---
title: 'Creación de un perfil de dispositivo de extensiones de kernel de macOS con Microsoft Intune: Azure | Microsoft Docs'
titleSuffix: ''
description: Agregue o cree un perfil de dispositivo de macOS y luego configure extensiones de kernel para permitir que el usuario invalide, agregue un identificador de equipo y un lote y un identificador de equipo en Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/24/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: annovich
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8f9212d275b17db6a40e3133b5363cd13c9d13d6
ms.sourcegitcommit: 7f17d6eb9dd41b031a6af4148863d2ffc4f49551
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "80551413"
---
# <a name="add-macos-kernel-extensions-in-intune"></a>Incorporación de extensiones de kernel de macOS en Intune

> [!NOTE]
> Las extensiones de kernel de macOS se van a reemplazar por extensiones del sistema. Para obtener más información, vea [Sugerencia de soporte técnico: Uso de extensiones del sistema en lugar de extensiones de kernel para macOS Catalina 10.15 en Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/support-tip-using-system-extensions-instead-of-kernel-extensions/ba-p/1191413).

En los dispositivos macOS, puede agregar características en el nivel de kernel. Estas características acceden a elementos del sistema operativo a los que no pueden hacerlo los programas normales. La organización puede tener necesidades o requisitos específicos que no están disponibles en una aplicación, una característica de dispositivo, etc. 

Para agregar extensiones de kernel que siempre se puedan cargar en los dispositivos, agregue "extensiones de kernel" (KEXT) en Microsoft Intune y luego implemente estas extensiones en los dispositivos.

Por ejemplo, tiene un programa antivirus que examina el dispositivo en busca de contenido malintencionado. Puede agregar la extensión de kernel de este programa antivirus como una extensión de kernel permitida en Intune. Luego, "asigne" la extensión a los dispositivos macOS.

Con esta característica, los administradores pueden permitir a los usuarios invalidar extensiones de kernel, agregar identificadores de equipo e incorporar extensiones de kernel concretas en Intune.

Esta característica se aplica a:

- macOS 10.13.2 y versiones posteriores

Para usar esta característica, los dispositivos deben estar:

- Inscritos en Intune mediante el Programa de inscripción de dispositivos (DEP) de Apple. [Inscripción automática de dispositivos macOS](../enrollment/device-enrollment-program-enroll-macos.md) tiene más información.

  O BIEN

- Inscritos en Intune con "inscripción de usuario aprobada" (término de Apple). [Prepararse para los cambios en las extensiones de kernel en macOS High Sierra](https://support.apple.com/en-us/HT208019) (abre el sitio web de Apple) tiene más información.

Intune usa "perfiles de configuración" para crear y personalizar estas configuraciones para las necesidades de su organización. Después de agregar estas características en un perfil, puede insertar o implementar el perfil en dispositivos macOS de su organización.

En este artículo se muestra cómo crear un perfil de configuración de dispositivo con extensiones de kernel en Intune.

> [!TIP]
> Para obtener más información sobre las extensiones de kernel, vea [Información general sobre las extensiones de kernel](https://developer.apple.com/library/archive/documentation/Darwin/Conceptual/KernelProgramming/Extend/Extend.html) (abre el sitio web de Apple).

## <a name="what-you-need-to-know"></a>Aspectos que debe saber

- Se pueden agregar extensiones de kernel heredadas sin firma.
- Asegúrese de escribir el identificador de equipo y el identificador de lote correctos de la extensión de kernel. Intune no valida los valores que se especifican. Si escribe información incorrecta, la extensión no funciona en el dispositivo. Un identificador de equipo tiene exactamente 10 caracteres alfanuméricos. 

> [!NOTE]
> Apple ha publicado información sobre la firma y la certificación para todo el software. En macOS 10.14.5 y versiones más recientes, las extensiones de kernel implementadas mediante Intune no tienen que cumplir la directiva de certificación de Apple.
>
> Para obtener información sobre esta directiva de certificación y las actualizaciones o los cambios, vea los siguientes recursos:
>
> - [Certificación de la aplicación antes de su distribución](https://developer.apple.com/documentation/security/notarizing_your_app_before_distribution) (abre el sitio web de Apple) 
> - [Prepararse para los cambios en las extensiones de kernel en macOS High Sierra](https://support.apple.com/en-us/HT208019) (abre el sitio web de Apple)

> [!NOTE]
> La interfaz de usuario de Intune se está actualizando a una experiencia de pantalla completa y puede tardar varias semanas. Hasta que el inquilino reciba esta actualización, tendrá un flujo de trabajo ligeramente diferente cuando cree o edite la configuración que se describe en este artículo.

## <a name="create-the-profile"></a>Creación del perfil

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Seleccione **Dispositivos** > **Perfiles de configuración** > **Crear perfil**.
3. Escriba las propiedades siguientes:

    - **Plataforma**: seleccione **macOS**.
    - **Perfil**: seleccione **Extensiones**.

4. Seleccione **Crear**.
5. En **Básico**, escriba las propiedades siguientes:

    - **Nombre**: escriba un nombre descriptivo para la directiva. Asígnele un nombre a las directivas para que pueda identificarlas de manera sencilla más adelante. Por ejemplo, un nombre de directiva válido es **macOS: Agregar extensiones de kernel a los dispositivos**.
    - **Descripción**: escriba una descripción para la directiva. Esta configuración es opcional pero recomendada.

6. Seleccione **Siguiente**.

7. En **Opciones de configuración**, establezca los parámetros:

    - [macOS](kernel-extensions-settings-macos.md)

8. Seleccione **Siguiente**.
9. En **Etiquetas de ámbito** (opcional), asigne una etiqueta para filtrar el perfil por grupos de TI específicos, como `US-NC IT Team` o `JohnGlenn_ITDepartment`. Para obtener más información sobre las etiquetas de ámbito, vea [Usar control de acceso basado en rol (RBAC) y etiquetas de ámbito](../fundamentals/scope-tags.md).

    Seleccione **Siguiente**.

10. En **Asignaciones**, seleccione los usuarios o grupos que van a recibir el perfil. Para obtener más información sobre la asignación de perfiles, vea [Asignación de perfiles de usuario y dispositivo](device-profile-assign.md).

    Seleccione **Siguiente**.

11. En **Revisar y crear**, revise la configuración. Si selecciona **Crear**, se guardan los cambios y se asigna el perfil. La directiva también se muestra en la lista de perfiles.

## <a name="next-steps"></a>Pasos siguientes

Una vez creado el perfil, está listo para asignarlo. Después, [asigne el perfil](device-profile-assign.md) y [supervise el estado](device-profile-monitor.md).
