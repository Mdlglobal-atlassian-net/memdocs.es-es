---
title: Eliminación de un usuario de un dispositivo iOS/iPadOS con Microsoft Intune
titleSuffix: ''
description: Obtenga información sobre cómo quitar un usuario de un dispositivo iOS/iPadOS compartido con Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: how-to
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ed91d31a7085d023ef012e1dd30d86c833819ecc
ms.sourcegitcommit: 302556d3b03f1a4eb9a5a9ce6138b8119d901575
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "83983068"
---
# <a name="remove-a-user-from-a-shared-iosipados-device"></a>Eliminación de un usuario de un dispositivo iOS/iPadOS compartido


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

La acción **Quitar usuario** elimina un usuario que seleccione de la memoria caché local en un dispositivo iPad compartido. El dispositivo iPad debe estar configurado para administrar la aplicación de Classroom de iOS/iPadOS mediante un [perfil educativo de iOS/iPadOS](../fundamentals/education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Plataformas admitidas

- Windows: no compatible
- Windows Phone: no compatible
- iOS/iPadOS: compatible con iOS/iPadOS 9.3 y versiones posteriores (solo dispositivos iPad compartidos)
- macOS: no compatible
- Android: no compatible

## <a name="remove-a-user"></a>Quitar un usuario

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Seleccione **Dispositivos** > **Todos los dispositivos**.
3. En la lista de dispositivos que administra, seleccione un dispositivo iOS/iPadOS.
4. En el panel del dispositivo, seleccione **Usuarios**.
5. En la lista, haga clic con el botón derecho en el usuario que quiere quitar y, después, seleccione **Quitar usuario**.

## <a name="next-steps"></a>Pasos siguientes

- Para ver el estado de la acción **Quitar usuario**, seleccione **Dispositivos** > **Acciones de dispositivo**.
