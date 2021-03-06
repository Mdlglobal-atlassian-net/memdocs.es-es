---
title: Configuración de la inscripción de dispositivos macOS
titleSuffix: Microsoft Intune
description: Descubra cómo configurar la inscripción de dispositivos macOS en Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/16/2019
ms.topic: overview
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3cd8c57dcaede1331838946d93c4fce16801651b
ms.sourcegitcommit: 302556d3b03f1a4eb9a5a9ce6138b8119d901575
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "83990506"
---
# <a name="set-up-enrollment-for-macos-devices-in-intune"></a>Configuración de la inscripción de dispositivos macOS en Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune le permite administrar dispositivos macOS para proporcionar a los usuarios acceso a las aplicaciones y el correo electrónico de empresa.

Como administrador de Intune, puede configurar la inscripción para dispositivos macOS propiedad de la empresa y dispositivos macOS de propiedad personal ("Bring Your Own Device" o BYOD). 

## <a name="prerequisites"></a>Requisitos previos

Complete los siguientes requisitos previos antes de configurar la inscripción de dispositivos macOS:

- [Asegúrese de que el dispositivo es apto para la inscripción de dispositivos de Apple](https://support.apple.com/en-us/HT204142#eligibility).
- [Configurar dominios](../fundamentals/custom-domain-name-configure.md)
- [Establecer la entidad de MDM](../fundamentals/mdm-authority-set.md)
- [Crear grupos](../fundamentals/groups-add.md)
- [Configurar el Portal de empresa](../apps/company-portal-app.md)
- Asignación de licencias de usuario en el [Centro de administración de Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Obtener un certificado push MDM de Apple](../enrollment/apple-mdm-push-certificate-get.md)

## <a name="user-owned-macos-devices-byod"></a>Dispositivos macOS propiedad del usuario (BYOD)

Puede permitir que los usuarios inscriban sus propios dispositivos personales en la administración de Intune. Esto se conoce como "bring your own device" o BYOD. Una vez completados los requisitos previos y asignadas las licencias a los usuarios, estos pueden inscribir sus dispositivos de estas maneras:
- visitando el [sitio web Portal de empresa](https://portal.manage.microsoft.com) o
- descargando Portal de empresa de Mac en [aka.ms/EnrollMyMac](https://aka.ms/EnrollMyMac).

También puede enviar a los usuarios un vínculo sobre los pasos de inscripción en línea: [Inscriba el dispositivo macOS en Intune](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-macos-cp).

Para más información acerca de otras tareas de usuario final, consulte estos artículos:

- [Recursos sobre la experiencia del usuario final con Microsoft Intune](../fundamentals/end-user-educate.md)
- [Usar un dispositivo macOS con Intune](../user-help/enroll-your-device-in-intune-macos-cp.md)

## <a name="company-owned-macos-devices"></a>Dispositivos macOS propiedad de la empresa
Para las organizaciones que adquieran dispositivos para sus usuarios, Intune admite los métodos de inscripción de dispositivos macOS propiedad de la empresa siguientes:
- [Inscripción de dispositivo automatizada (ADE) de Apple](device-enrollment-program-enroll-macos.md): las organizaciones pueden adquirir dispositivos macOS a través de ADE. ADE permite implementar un perfil de inscripción "de forma inalámbrica" para incluir los dispositivos en la administración.
- [Administrador de inscripción de dispositivos (DEM)](device-enrollment-manager-enroll.md): puede usar una cuenta de DEM para inscribir hasta 1000 dispositivos.

## <a name="block-macos-enrollment"></a>Bloqueo de la inscripción de macOS
De forma predeterminada, Intune permite la inscripción de dispositivos macOS. Para bloquear la inscripción de dispositivos macOS, vea [Set device type restrictions](enrollment-restrictions-set.md) (Establecer restricciones de tipos de dispositivo).

## <a name="enroll-virtual-macos-machines-for-testing"></a>Inscribir máquinas virtuales macOS para realizar pruebas

> [!NOTE]
> Las máquinas virtuales macOS solo se pueden usar para efectuar pruebas. No las use como dispositivos de producción para los usuarios finales. 

Las máquinas virtuales macOS se pueden inscribir con Parallels Desktop o con VMware Fusion para realizar pruebas en ellas. 

Si se usa Parallels Desktop, hay que indicar el tipo de hardware y el número de serie de las máquinas virtuales para que Intune pueda reconocerlas. Siga las instrucciones de Parallels para establecer el tipo de hardware y el [número de serie](http://kb.parallels.com/123455) con objeto de configurar los valores necesarios para las pruebas. Es recomendable que el tipo de hardware del dispositivo donde se ejecutan las máquinas virtuales y el tipo de hardware de las máquinas virtuales que vaya a crear sea el mismo. El tipo de hardware se encuentra en **menú Apple** > **Acerca de este Mac** > **Información del Sistema** > **Identificador del modelo**. 

En el caso de VMware Fusion, hay que [editar el archivo .vmx](https://kb.vmware.com/s/article/1014782) para establecer el modelo de hardware y el número de serie de la máquina virtual. Es recomendable que el tipo de hardware del dispositivo donde se ejecutan las máquinas virtuales y el tipo de hardware de las máquinas virtuales que vaya a crear sea el mismo. El tipo de hardware se encuentra en **menú Apple** > **Acerca de este Mac** > **Información del Sistema** > **Identificador del modelo**. 

## <a name="user-approved-enrollment"></a>Inscripción aprobada por el usuario
La inscripción de MDM aprobada por el usuario es un tipo de inscripción de macOS que se puede usar para administrar cierta configuración relacionada con la seguridad. Para más información, consulte la [documentación de soporte técnico de Apple](https://support.apple.com/HT208019).  
 
Durante el proceso de inscripción de BYOD, se le pedirá al usuario que apruebe manualmente el perfil de administración de Apple. Las instrucciones se proporcionan en la aplicación Portal de empresa para macOS. Aunque no es necesario aprobar el perfil de administración para completar la inscripción, Intune recomienda las inscripciones aprobadas por el usuario. Si el usuario no aprueba el perfil durante la inscripción, el usuario puede ir a **Preferencias del sistema** > **Perfiles**, elegir el perfil de administración y seleccionar **Aprobar**.    

### <a name="find-out-if-a-device-is-user-approved"></a>Determinación de si un dispositivo está aprobado por el usuario
1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Elija **Dispositivos** > **Todos los dispositivos** > elija el dispositivo > **Hardware**.
3. Compruebe el campo **Inscripción de usuario aprobada**.


## <a name="next-steps"></a>Pasos siguientes

Una vez que los dispositivos macOS se hayan inscrito, puede [crear una configuración personalizada para dispositivos macOS](../configuration/custom-settings-macos.md).
