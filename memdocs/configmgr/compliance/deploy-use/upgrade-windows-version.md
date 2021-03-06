---
title: Actualización de dispositivos Windows a una versión diferente
titleSuffix: Configuration Manager
description: Use Configuration Manager para actualizar automáticamente los dispositivos Windows 10 a otra edición de Windows.
ms.date: 09/03/2019
ms.prod: configuration-manager
ms.technology: configmgr-compliance
ms.topic: conceptual
ms.assetid: b0c9db74-841e-46eb-8924-957cde968bf7
author: aczechowski
ms.author: aaroncz
manager: dougeby
ms.openlocfilehash: 77ef255a820104ef2042a370b5056677fddb9d12
ms.sourcegitcommit: bbf820c35414bf2cba356f30fe047c1a34c5384d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "81692303"
---
# <a name="upgrade-windows-devices-to-a-new-edition-with-configuration-manager"></a>Actualización de dispositivos Windows a una edición nueva con Configuration Manager

*Se aplica a: Configuration Manager (rama actual)*

La **Directiva de actualización de edición** permite actualizar automáticamente los dispositivos con Windows 10 a una edición diferente.

Las siguientes rutas de acceso de actualización son compatibles:

- Desde Windows 10 Pro a Windows 10 Enterprise
- Desde Windows 10 Home a Windows 10 Education
- De Windows 10 Mobile a Windows 10 Mobile Enterprise

Los dispositivos deben ejecutar el software cliente de Configuration Manager. No se admiten los dispositivos administrados por [MDM local](../../mdm/understand/manage-mobile-devices-with-on-premises-infrastructure.md).

## <a name="before-you-start"></a>Antes de empezar

Antes de empezar a actualizar dispositivos a la versión más reciente, consulte los requisitos previos siguientes:  

- Para las ediciones de escritorio de Windows 10: una clave de producto válida para la nueva versión de Windows en todos los dispositivos donde quiera aplicar la directiva. Esta clave de producto puede ser una clave de activación múltiple (CAM) o una clave de licencias por volumen genérica (CLVG). Las CLVG también se conocen como claves de configuración de cliente del servicio de administración de claves (SAC). Para obtener más información, consulte [Plan para la activación por volumen](https://docs.microsoft.com/windows/deployment/volume-activation/plan-for-volume-activation-client). Para obtener una lista de claves de configuración de cliente KMS, consulte el [Apéndice A](https://docs.microsoft.com/windows-server/get-started/kmsclientkeys) de la Guía de activación de Windows Server. <!--496871-->  

- Para Windows 10 Mobile: un archivo de licencia XML del Centro de servicios de licencias por volumen (VLSC) de Microsoft. Este archivo contiene la información de licencia para la nueva versión de Windows en todos los dispositivos de destino de la directiva.

- Para administrar este tipo de directiva, debe ocupar el rol de seguridad de **Administrador total** de Configuration Manager.

## <a name="configure-the-policy"></a>Configuración de la directiva  

1. En la consola de Configuration Manager, vaya al área de trabajo **Activos y compatibilidad**, expanda **Configuración de cumplimiento** y seleccione el nodo **Actualización de edición de Windows 10**.  

2. En la pestaña **Inicio** de la cinta, en el grupo **Crear**, seleccione **Crear directiva de actualización de la edición**.  

3. Seleccione **Crear directiva**.  

4. En la página **General** del **Asistente para la creación de directiva de actualización de la edición**, especifique la información siguiente:  

    - **Nombre**: escriba un nombre para la directiva de actualización de ediciones.  

    - **Descripción** (opcional): si quiere, escriba una descripción de la directiva que le ayude a identificarla en la consola de Configuration Manager.  

    - **SKU a la que actualizará el dispositivo**: en la lista desplegable, seleccione la edición de destino de Windows 10 Escritorio o Windows 10 Mobile.  

    - **Información de la licencia**: seleccione una de las opciones siguientes:  

        - **Clave de producto**: escriba una clave de producto válida para la edición de destino de Windows 10 Escritorio.  

            > [!NOTE]  
            > Después de crear una directiva que contenga una clave de producto, esta última no se podrá editar más adelante. Configuration Manager oculta la clave por motivos de seguridad. Para cambiar la clave de producto, vuelva a escribir toda la clave.  

        - **Archivo de licencia**: seleccione **Examinar** para elegir un archivo de licencia válido en formato XML. Configuration Manager usa este archivo de licencia para actualizar los dispositivos de Windows 10 Mobile.  

5. Complete el asistente.  

## <a name="deploy-the-policy"></a>Implementar la directiva  

1. En la consola de Configuration Manager, vaya al área de trabajo **Activos y compatibilidad**, expanda **Configuración de cumplimiento** y seleccione el nodo **Actualización de edición de Windows 10**.  

2. Seleccione la directiva de actualización de la edición de Windows 10 que quiera implementar. En la pestaña **Inicio** de la cinta de opciones, vaya al grupo **Implementación** y seleccione **Implementar**.  

3. Seleccione la colección de dispositivos en la que quiera implementar la directiva.

4. Seleccione la programación mediante la cual el cliente evalúa la directiva.

5. Complete el asistente.

## <a name="next-steps"></a>Pasos siguientes

Supervise esta implementación desde el nodo **Implementaciones** del espacio de trabajo **Supervisión**. Si ve errores que indican un error de implementación, por ejemplo:

- **No se aplica a este dispositivo**
- **Error de conversión de tipo de datos**

Estos errores no significan que hubo un error en la implementación. En el dispositivo de destino, compruebe que la actualización se realizó correctamente.

Una vez que el cliente haya evaluado la directiva de destino, aplicará la actualización en un plazo de dos horas. [Algunas versiones de Windows](https://docs.microsoft.com/windows/deployment/upgrade/windows-10-edition-upgrades) pueden requerir un reinicio en ese momento. Asegúrese de informar a los usuarios a los que implemente la directiva o prográmela para que se ejecute fuera del horario laboral de los usuarios.

Si aparece el siguiente error en **DcmWmiProvider.log** en el cliente, asegúrese de usar la clave correcta para su escenario de activación. Para obtener más información, consulte la sección [Antes de empezar](#before-you-start). Si usa un servicio de administración de claves (KMS) para la activación, asegúrese de usar una [clave de configuración de cliente KMS](https://docs.microsoft.com/windows-server/get-started/kmsclientkeys).  <!-- 496871 -->

`Failed to execute CheckApplicabilityMethod with error = 0x80041001 OsEditionUpgradeProvider`

## <a name="see-also"></a>Vea también

- [Planeación de activación por volumen](https://docs.microsoft.com/windows/deployment/volume-activation/plan-for-volume-activation-client)

- [Actualización de edición de Windows 10](https://docs.microsoft.com/windows/deployment/upgrade/windows-10-edition-upgrades)

- [Actualización de las ediciones de Windows 10 o desactivación del modo S en dispositivos con Microsoft Intune](https://docs.microsoft.com/intune/edition-upgrade-configure-windows-10)
