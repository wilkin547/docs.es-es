---
title: Cómo habilitar la detección de reproducción de tokens
ms.date: 03/30/2017
ms.assetid: 5a9f5771-f5f6-4100-8501-406aa20d731a
author: BrucePerlerMS
ms.openlocfilehash: a357f153d61b6a8e1e105639bd68647dabdc26f8
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336530"
---
# <a name="how-to-enable-token-replay-detection"></a>Cómo habilitar la detección de reproducción de tokens
## <a name="applies-to"></a>Se aplica a  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   Formularios Web Forms ASP.NET®  
  
## <a name="summary"></a>Resumen  
 En este tema de procedimientos se detallan los procedimientos necesarios para habilitar la detección de reproducción de tokens en una aplicación ASP.NET que usa WIF. También se proporcionan instrucciones para probar la aplicación a fin de comprobar que esté habilitada la detección de reproducción de tokens. Esta sección de procedimientos no tiene instrucciones detalladas para crear un servicio de token de seguridad (STS) y en su lugar se utiliza el STS de desarrollo que se incluye con la extensión Identity and Access Tool. El STS de desarrollo no realiza la autenticación real y está pensado únicamente para pruebas. Para completar este procedimiento, tendrá que instalar la extensión Identity and Access Tool. Se puede descargar desde la ubicación siguiente: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)  
  
## <a name="contents"></a>Contenido  
  
-   Objetivos  
  
-   Información general  
  
-   Resumen de pasos  
  
-   Paso 1 - Crear una aplicación de formularios Web Forms ASP.NET simple y habilitar la detección de reproducción  
  
-   Paso 2 – Probar la solución  
  
## <a name="objectives"></a>Objetivos  
  
-   Crear una aplicación ASP.NET simple que use WIF y el STS de desarrollo desde la herramienta Identity and Access Tool  
  
-   Habilitar la detección de reproducción de tokens y comprobar que funciona  
  
## <a name="overview"></a>Información general  
 Los ataques de reproducción se producen cuando un cliente intenta autenticarse en un usuario de confianza con un token STS que ya ha usado. Para evitar este tipo de ataque, WIF contiene una caché de detección de reproducción de tokens STS ya usados. Cuando está habilitada, la detección de reproducción comprueba el token de la solicitud entrante y verifica si el token ya se ha usado. Si el token ya se ha usado, se rechaza la solicitud y se produce una excepción <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException>.  
  
 En los pasos siguientes se muestran los cambios de configuración necesarios para habilitar la detección de reproducción.  
  
## <a name="summary-of-steps"></a>Resumen de pasos  
  
-   Paso 1 - Crear una aplicación de formularios Web Forms ASP.NET simple y habilitar la detección de reproducción  
  
-   Paso 2 – Probar la solución  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application-and-enable-replay-detection"></a>Paso 1 - Crear una aplicación de formularios Web Forms ASP.NET simple y habilitar la detección de reproducción  
 En este paso, creará una aplicación de formularios Web Forms de ASP.NET y modificará el archivo *Web.config* para habilitar la detección de reproducción.  
  
#### <a name="to-create-a-simple-aspnet-application"></a>Para crear una aplicación de ASP.NET sencilla  
  
1. Inicie Visual Studio y haga clic en **Archivo**, **Nuevo** y, luego, en **Proyecto**.  
  
2. En la ventana **Nuevo proyecto**, haga clic en **Aplicación de formularios Web Forms ASP.NET**.  
  
3. En **Nombre**, escriba `TestApp` y haga clic en **Aceptar**.  
  
4. Haga clic con el botón derecho en el proyecto **TestApp** en el **Explorador de soluciones** y seleccione **Identity and Access**.  
  
5. Aparecerá la ventana **Identity and Access**. En **Proveedores**, seleccione **Test your application with the Local Development STS** (Probar la aplicación con el STS de desarrollo local) y haga clic en **Aplicar**.  
  
6. Agregue el siguiente elemento **\<tokenReplayDetection>** al archivo de configuración *Web.config* inmediatamente después de los elementos **\<system.identityModel>** e **\<identityConfiguration>**, como se muestra a continuación:  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration>  
            <tokenReplayDetection enabled="true"/>  
    ```  
  
## <a name="step-2--test-your-solution"></a>Paso 2 – Probar la solución  
 En este paso, probará la aplicación ASP.NET habilitada para WIF a fin de comprobar que se ha habilitado la detección de reproducción.  
  
#### <a name="to-test-your-wif-enabled-aspnet-application-for-replay-detection"></a>Para probar la aplicación ASP.NET habilitada para WIF para la detección de reproducción  
  
1. Presione la tecla **F5** para ejecutar la solución. Debe aparecer la página principal de ASP.NET predeterminada y se le debe autenticar automáticamente con el nombre de usuario *Terry*, que es el usuario predeterminado devuelto por el STS de desarrollo.  
  
2. Haga clic en el botón **Atrás** del explorador. Debe estar presente con un **Server Error in '/' Application** página con la siguiente descripción: *ID1062: Se detectó la reproducción para: Símbolo (token): 'System.IdentityModel.Tokens.SamlSecurityToken'*, seguido de un *AssertionId* y un *emisor*.  
  
     Está viendo esta página de error porque se ha producido una excepción de tipo <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> al detectarse la reproducción de tokens. Este error se produce porque está intentando volver a enviar la solicitud POST inicial cuando el token se presenta por primera vez. El botón **Atrás** no provocará este comportamiento en las solicitudes siguientes al servidor.
