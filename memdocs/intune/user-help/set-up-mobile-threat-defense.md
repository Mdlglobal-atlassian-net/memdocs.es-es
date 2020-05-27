---
title: Instalación de Mobile Threat Defense en su dispositivo móvil
description: Aprenda a instalar Mobile Threat Defense en su dispositivo móvil.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/27/2020
ms.topic: end-user-help
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: 5df46a4632b198b4b4916f5ce5165b3f116ccac9
ms.sourcegitcommit: a77ba49424803fddcaf23326f1befbc004e48ac9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "83881873"
---
# <a name="install-mobile-threat-defense"></a>Instalación de Mobile Threat Defense   

Como parte de los requisitos de seguridad de su organización, es posible que deba instalar una aplicación de proveedor de Mobile Threat Defense (MTD). Este tipo de aplicación detecta y comunica las amenazas presentes en el dispositivo, como aplicaciones sospechosas, redes o vulnerabilidades del sistema operativo.  

Si no tiene la aplicación MTD necesaria, no podrá iniciar sesión en las aplicaciones protegidas con su cuenta profesional o educativa. En este artículo, aprenderá a [instalar una aplicación MTD](set-up-mobile-threat-defense.md#install-app) para desbloquear su acceso.  

Hay una gran variedad de aplicaciones de proveedor de MTD disponibles para instalar, todas ellas con nombres diferentes. Su organización le informará de cuál debe usar. Si se le pide que instale la aplicación pero no se proporcionan instrucciones adicionales o un vínculo para obtener la aplicación, póngase en contacto con el personal de soporte técnico de TI. 


## <a name="information-your-organization-can-see"></a>Información que puede ver su organización   

Su organización no puede ver ningún dato, como textos, correos electrónicos e imágenes, en sus aplicaciones personales. La aplicación MTD informa sobre las aplicaciones, como el nombre y la versión, a su organización. La información real que se notifique dependerá del proveedor de MTD que use su empresa. Es posible que su organización vea lo siguiente:   

* Nombre de la aplicación  
* Id. de aplicación: nombre único que identifica a la aplicación en Google Play.  
* Versión de la aplicación y número de versión corto: números de versión específicos de una aplicación.  
* Lote de aplicaciones y tamaño dinámico: cantidad de espacio que usa una aplicación en el dispositivo. 


## <a name="install-app"></a>Instalación de aplicación    
Al iniciar sesión en una aplicación protegida, se le pedirá automáticamente que instale una aplicación MTD. Siga los pasos en pantalla para completar la instalación. Siga los pasos de esta sección para obtener ayuda adicional.  
 
También es posible que se le pida que registre el dispositivo. El registro es necesario para confirmar su identidad y conectar su cuenta profesional o educativa al dispositivo. Si no se ha registrado, se le guiará automáticamente a través de ese programa de instalación antes de instalar la aplicación MTD. Cuando llegue a la pantalla **Obtener acceso**, podrá iniciar los pasos de instalación.  

Para obtener más información sobre el registro de dispositivos, vea [Registro de su dispositivo personal en la red de su organización](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network).  

### <a name="ios-setup"></a>Configuración de iOS  

1. En la pantalla **Obtener acceso**, siga las instrucciones para instalar la aplicación MTD requerida por su organización.   
2. Vuelva a la pantalla **Obtener acceso** y seleccione **Abrir**.  
3. La aplicación MTD solicita permiso para abrir Microsoft Authenticator. Seleccione **Abrir**. 
4. Seleccione su cuenta profesional para iniciar sesión. 
5. Espere mientras la aplicación MTD examina el dispositivo en busca de amenazas de seguridad. 
6. Vuelva a la aplicación educativa o de trabajo a la que estaba intentando acceder inicialmente. En este punto, su organización podría pedirle que configurase otros requisitos de seguridad de la aplicación, como un PIN.   
7. Ahora debería tener acceso a la aplicación. Si todavía está bloqueado:  
    * En la pantalla **Obtener acceso**, seleccione **Volver a comprobar**.  
    * Vaya a la aplicación MTD y compruebe si hay amenazas existentes. Complete los pasos recomendados para resolver la amenaza y recuperar el acceso.    

### <a name="android-setup"></a>Configuración de Android 

1. En la pantalla **Obtener acceso**, siga las instrucciones para instalar la aplicación MTD requerida por su organización.  
2. Vuelva a la pantalla **Obtener acceso** y seleccione **Abrir**.  
3. La aplicación MTD solicita permiso para acceder a determinadas áreas del dispositivo, en caso de que sea necesario. Para que esta aplicación funcione correctamente, debe **permitir** el acceso a los contactos. Los permisos solicitados variarán en los proveedores de MTD.  
4. Seleccione su cuenta profesional para iniciar sesión.  
5. Espere mientras la aplicación MTD examina el dispositivo en busca de amenazas de seguridad.  
6. Vuelva a la aplicación educativa o de trabajo a la que estaba intentando acceder inicialmente. En este punto, su organización podría pedirle que configurase otros requisitos de seguridad de la aplicación, como un PIN.  
7. Ahora debería tener acceso a la aplicación. Si todavía está bloqueado:  
    * En la pantalla **Obtener acceso**, seleccione **Volver a comprobar**.  
    * Vaya a la aplicación MTD y compruebe si hay amenazas existentes. Complete los pasos recomendados para resolver la amenaza y recuperar el acceso.  

### <a name="installation-failed"></a>Error de instalación  

Si se produce un error en la instalación, póngase en contacto con el personal de soporte técnico de TI. Vaya al [sitio web Portal de empresa](https://go.microsoft.com/fwlink/?linkid=2010980) para buscar la información de contacto de su empresa.  

También puede enviar los registros de la aplicación al personal de soporte técnico de TI para proporcionarles más contexto sobre la instalación.  
* Usuarios de Android: [Cargue y envíe por correo electrónico los registros](https://docs.microsoft.com/mem/intune/user-help/send-logs-to-your-it-admin-by-email-android) desde Portal de empresa.   

* Usuarios de dispositivos iOS: [Recupere y envíe los registros](https://docs.microsoft.com/intune/apps/manage-microsoft-edge#use-microsoft-edge-to-access-managed-app-logs) desde Microsoft Edge para iOS.  

## <a name="resolve-a-threat"></a>Resolución de amenazas  
Si una amenaza supera el nivel definido por la organización, la organización podrá:  
   
* Bloquear acceso: impide que use las aplicaciones protegidas de su organización mientras tenga la sesión iniciada con su cuenta profesional o educativa.  
* Borrar datos: elimina los datos profesionales o educativos de una o varias aplicaciones protegidas de su organización.  

Para resolver una amenaza y recuperar el acceso, abra la aplicación MTD en el dispositivo. Lea la información proporcionada para obtener información sobre cómo la amenaza podría afectar al dispositivo y cómo resolverla. Después de seguir los pasos para resolver la amenaza, vuelva a la aplicación MTD e inicie un nuevo examen. Puede tardar unos minutos en recuperar el acceso a su organización.  

## <a name="next-steps"></a>Pasos siguientes  

¿Aún necesita ayuda? Póngase en contacto con el departamento de soporte técnico de la empresa. Para averiguar su información de contacto, vaya al [sitio web del portal de empresa](https://go.microsoft.com/fwlink/?linkid=2010980).

