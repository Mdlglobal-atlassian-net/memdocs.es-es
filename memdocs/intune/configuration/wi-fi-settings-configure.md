---
title: Creación de un perfil de Wi-Fi para dispositivos en Microsoft Intune - Azure | Microsoft Docs
description: Consulte estos pasos para crear un perfil de configuración de dispositivos Wi-Fi en Microsoft Intune. Cree perfiles para Android, Android Enterprise, quiosco de Android, iOS, iPadOS, macOS, Windows 10 y versiones posteriores, y Windows Holographic for Business. Use estos perfiles para crear una conexión Wi-Fi para usar certificados, elegir un tipo de EAP, seleccionar un método de autenticación, habilitar un proxy y mucho más.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: tycast
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5297f87dd3aad6b88281b491ccb7c1f0878ffc1e
ms.sourcegitcommit: 3d895be2844bda2177c2c85dc2f09612a1be5490
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "79343133"
---
# <a name="add-and-use-wi-fi-settings-on-your-devices-in-microsoft-intune"></a>Adición y uso de la configuración de Wi-Fi en los dispositivos en Microsoft Intune

Wi-Fi es una red inalámbrica que muchos dispositivos móviles utilizan para acceder a la red. Microsoft Intune incluye configuraciones Wi-Fi integradas que se pueden implementar en usuarios y dispositivos de su organización. Este grupo de configuración se conoce como un "perfil" y se puede asignar a distintos usuarios y grupos. Una vez asignado, los usuarios acceden a la red Wi-Fi de la organización sin tener que configurarla ellos mismos.

Por ejemplo, instale una nueva red Wi-Fi denominada Contoso Wi-Fi. Después, quiere configurar todos los dispositivos iOS/iPadOS para conectarse a esta red. Este es el proceso:

1. Cree un perfil de Wi-Fi que contenga la configuración para conectarse a la red inalámbrica Contoso Wi-Fi.
2. Asigne el perfil a un grupo que incluya todos los usuarios de los dispositivos iOS/iPadOS.
3. Los usuarios encuentran la nueva red Contoso Wi-Fi en la lista de redes inalámbricas de su dispositivo. Pueden conectarse a ella fácilmente con el método de autenticación de su elección.

En este artículo se enumeran los pasos para crear un perfil Wi-Fi. También incluye vínculos que describen las distintas configuraciones para cada plataforma.

## <a name="supported-device-platforms"></a>Plataformas de dispositivos compatibles

Los perfiles de Wi-Fi admiten las siguientes plataformas de dispositivo:

- Android 4 y versiones posteriores
- Quiosco de Android y Android Enterprise
- iOS 8.0 y versiones posteriores
- IPadOS 13.0 y versiones más recientes
- macOS X 10.11 y versiones más recientes
- Windows 10 y versiones posteriores, Windows 10 Mobile y Windows Holographic for Business

> [!NOTE]
> Para dispositivos que ejecutan Windows 8.1, puede importar una configuración de Wi-Fi que se haya exportado anteriormente desde otro dispositivo.

## <a name="create-a-device-profile"></a>Creación del perfil de un dispositivo

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Seleccione **Dispositivos** > **Perfiles de configuración** > **Crear perfil**.
3. Escriba las propiedades siguientes:

    - **Nombre**: escriba un nombre descriptivo para el nuevo perfil. Asígnele un nombre a los perfiles para que pueda identificarlos de manera sencilla más adelante. Por ejemplo, un buen nombre de perfil sería **Perfil WiFi para toda la empresa**.
    - **Descripción**: escriba una descripción para el perfil. Esta configuración es opcional pero recomendada.
    - **Plataforma**: seleccione la plataforma de los dispositivos. Las opciones son:

      - **Android**
      - **Android Enterprise**
      - **iOS/iPadOS**
      - **macOS**
      - **Windows 8.1 y versiones posteriores**
      - **Windows 10 y versiones posteriores**

    - **Tipo de perfil**: Seleccione **Wi-Fi**.

      > [!TIP]
      >
      > - Para dispositivos **Android Enterprise** que se ejecutan como un dispositivo dedicado (quiosco), elija **Solo el propietario del dispositivo** > **Wi-Fi**.
      > - Para **Windows 8.1 y versiones posteriores**, puede elegir **Importación de Wi-Fi**. Esta opción le permite importar la configuración de Wi-Fi como archivo XML exportado previamente de otro dispositivo.

4. Alguna configuración de Wi-Fi varía en función de la plataforma. Para ver la configuración de una plataforma concreta, elija la plataforma:

    - [Android](wi-fi-settings-android.md)
    - [Android Enterprise](wi-fi-settings-android-enterprise.md), incluidos los dispositivos dedicados
    - [iOS/iPadOS](wi-fi-settings-ios.md)
    - [macOS](wi-fi-settings-macos.md)
    - [Windows 10 y versiones posteriores](wi-fi-settings-windows.md)
    - [Windows 8.1 y versiones posteriores](wi-fi-settings-import-windows-8-1.md), incluido Windows Holographic for Business

5. Cuando termine, seleccione **Crear perfil** > **Crear**.

El perfil se crea y se muestra en la lista de perfiles (**Configuración del dispositivo** > **Perfiles**).

## <a name="next-steps"></a>Pasos siguientes

Se crea el perfil, pero no hacen nada. Después, [asigne este perfil](device-profile-assign.md) y [supervise su estado](device-profile-monitor.md).

[Problemas de perfiles Wi-Fi en Intune](troubleshoot-wi-fi-profiles.md).