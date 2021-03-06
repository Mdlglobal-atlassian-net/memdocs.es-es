---
title: Ubicaciones de archivo de base de datos personalizadas
titleSuffix: Configuration Manager
description: Obtenga información sobre cómo especificar ubicaciones personalizadas para archivos de base de datos de SQL Server.
ms.date: 10/06/2016
ms.prod: configuration-manager
ms.technology: configmgr-core
ms.topic: conceptual
ms.assetid: 500a9aa6-68aa-44eb-bf49-350c1314a697
author: mestew
ms.author: mstewart
manager: dougeby
ms.openlocfilehash: d3f01e54ba196ee9c27295d8f970a7dbe352f63f
ms.sourcegitcommit: 214fb11771b61008271c6f21e17ef4d45353788f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82906188"
---
# <a name="custom-locations-for-configuration-manager-site-database-files"></a>Ubicaciones personalizadas para archivos de base de datos del sitio de Configuration Manager

*Se aplica a: Configuration Manager (rama actual)*

 Configuration Manager es compatible con las ubicaciones personalizadas de los archivos de base de datos de SQL Server.  

> [!NOTE]  
>  La opción de especificar ubicaciones de archivos no predeterminadas no está disponible cuando se usa un clúster de SQL Server.  

 **Durante la configuración** de un nuevo sitio principal o un sitio de administración central, puede hacer lo siguiente:  

-   **Especificar ubicaciones de archivo no predeterminadas para la base de datos del sitio**: después, el programa de instalación de Configuration Manager crea la base de datos del sitio mediante estas ubicaciones.  

-   **Especificar el uso de una base de datos de SQL Server existente que use ubicaciones de archivo personalizadas**:  después, el programa de instalación de Configuration Manager usa esa base de datos existente y las ubicaciones de archivo preconfiguradas.  

**Después de la configuración**, puede cambiar la ubicación de los archivos de la base de datos del sitio. Para ello, es necesario detener el sitio y editar la ubicación de los archivos en SQL Server:  

-   En el servidor de sitio de Configuration Manager, detenga el servicio **SMS_Executive**.  

-   Para obtener más información sobre cómo se mueve una base de datos de usuario, vea [Mover bases de datos de usuario](https://docs.microsoft.com/sql/relational-databases/databases/move-user-databases?view=sql-server-2014).  

-   Después de completar el movimiento de archivos de la base de datos, reinicie el servicio **SMS_Executive** en el servidor de sitio de Configuration Manager.  
