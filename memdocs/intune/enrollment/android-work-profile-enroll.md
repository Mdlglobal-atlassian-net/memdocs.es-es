---
title: Inscripción de dispositivos del perfil de trabajo de Android Enterprise en Intune
titleSuffix: Microsoft Intune
description: Aprenda a inscribir dispositivos del perfil de trabajo de Android Enterprise en Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 5/13/2019
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c3da384efb87e5510e64954ed7b1badfb98f6583
ms.sourcegitcommit: 302556d3b03f1a4eb9a5a9ce6138b8119d901575
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "83987514"
---
# <a name="set-up-enrollment-of-android-enterprise-work-profile-devices"></a>Configuración de la inscripción de dispositivos del perfil de trabajo de Android Enterprise

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune lo ayuda a implementar aplicaciones y opciones de configuración en dispositivos del perfil de trabajo de Android Enterprise a fin de garantizar que la información laboral y la personal se mantengan aparte. Para más detalles sobre Android Enterprise, vea [Requisitos para usar dispositivos Android en una empresa](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Para configurar la administración de perfiles de trabajo Android Enterprise, siga estos pasos:

1. [Conecte su cuenta de inquilino de Intune a su cuenta de Android Enterprise](connect-intune-android-enterprise.md).
2. Especifique la configuración de inscripción del perfil de trabajo Android Enterprise. Los perfiles de trabajo Android Enterprise [solo se admiten en determinados dispositivos Android](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22). Cualquier dispositivo que admita perfiles de trabajo de Android Enterprise también admite la administración del administrador de dispositivos Android. Intune permite especificar cómo se deben administrar los dispositivos que admiten los perfiles de trabajo Android Enterprise en [Restricciones de inscripción](enrollment-restrictions-set.md).
    - **Bloquear**:  Todos los dispositivos Android, incluidos los que admiten perfiles de trabajo de Android Enterprise, se inscribirán como dispositivos del administrador de dispositivos Android, a menos que también se bloquee la inscripción del administrador de dispositivos Android. 
    - **Permitir (opción predeterminada)** : todos los dispositivos que admiten perfiles de trabajo Android Enterprise se inscribirán como dispositivos de trabajo Android Enterprise. Todos los dispositivos Android que no admiten perfiles de trabajo de Android Enterprise, se inscriben como dispositivos del administrador de dispositivos Android, a menos que se bloquee la inscripción del administrador de dispositivos Android. 
> [!NOTE]
> El valor predeterminado establecido en **Permitir** se cumple para los nuevos inquilinos a partir de julio de 2019. Los inquilinos anteriores no experimentarán ningún cambio en sus restricciones de inscripción y verán las directivas que se hayan establecido en Restricciones de Inscripción. En el caso de los inquilinos anteriores que nunca hayan sufrido cambios en las restricciones de inscripción, **Bloquear** seguirá siendo el valor predeterminado para los perfiles de trabajo de Android Enterprise.

3. [Indique a los usuarios cómo deben inscribir sus dispositivos](../user-help/enroll-device-android-work-profile.md).  

Si quiere inscribir dispositivos con perfiles de trabajo de Android Enterprise, pero esos dispositivos ya se han inscrito anteriormente con el administrador de dispositivos Android, debe anular su inscripción y volver a inscribirlos.
> [!NOTE]
> Como administrador, puede hacerlo de forma remota con la función **Retirar**. Esta función se encuentra en el menú de acciones después de seleccionar el dispositivo en la hoja **Todos los dispositivos**.

Si va a inscribir dispositivos de perfil de trabajo Android Enterprise a través de una cuenta [administrador de inscripciones de dispositivos](device-enrollment-manager-enroll.md), existe un límite de 10 dispositivos que se pueden inscribir por cuenta.

Para obtener más información, consulte [Datos que Intune manda a Google](../protect/data-intune-sends-to-google.md).

## <a name="next-steps-for-android-enterprise-work-profiles"></a>Pasos siguientes para los perfiles de trabajo de Android Enterprise
- [Implementación de aplicaciones del perfil de trabajo de Android Enterprise](../apps/apps-add-android-for-work.md)
- [Incorporación de directivas de configuración del perfil de trabajo de Android Enterprise](../configuration/device-profiles.md)

## <a name="see-also"></a>Vea también

[Configuración y solución de problemas de dispositivos de Android Enterprise en Microsoft Intune](https://support.microsoft.com/help/4476974)
