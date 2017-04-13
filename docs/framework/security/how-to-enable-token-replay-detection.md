---
title: "C&#243;mo: Habilitar la detecci&#243;n de reproducci&#243;n de tokens | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5a9f5771-f5f6-4100-8501-406aa20d731a
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# C&#243;mo: Habilitar la detecci&#243;n de reproducci&#243;n de tokens
## Se aplica a  
  
-   Base \(WIF\) de identidad de Microsoft® Windows®  
  
-   Formularios Web Forms de ASP.NET®  
  
## Resumen  
 En este procedimiento proporciona los procedimientos paso a paso detallados para habilitar la detección de la respuesta del token en una aplicación ASP.NET que utilice WIF.  También proporciona instrucciones sobre cómo probar la aplicación para comprobar que la detección de la respuesta del token está habilitada.  En este procedimiento no tiene instrucciones detalladas para crear un Servicio de token de seguridad \(STS\) y, en su lugar utiliza el desarrollo STS que procede de la identidad y la herramienta de accesibilidad.  El desarrollo STS no realiza la autenticación real y está pensado para comprobar únicamente.  Necesitará instalar la identidad y la herramienta de accesibilidad para completar esta práctico.  Puede descargar de la siguiente ubicación: [identidad y herramienta de accesibilidad](http://go.microsoft.com/fwlink/?LinkID=245849)  
  
## Contenido  
  
-   Objetivos  
  
-   Información general  
  
-   Resumen de pasos  
  
-   Paso 1 \- cree una aplicación de formularios Web Forms sencillo ASP.NET y habilitar la detección de la respuesta  
  
-   Paso 2 \- pruebe la solución  
  
## Objetivos  
  
-   Cree una aplicación sencilla de ASP.NET que utilice WIF y desarrollo STS de identidad y la herramienta de accesibilidad  
  
-   Habilitar la detección de la respuesta del token y compruebe que está trabajando  
  
## Información general  
 Un ataque de reproducción se produce cuando un cliente intenta autenticar a un usuario de confianza con un token de STS que el cliente ya ha utilizado.  Para ayudar a evitar este ataque, WIF contiene la memoria caché de detección de respuesta de tokenes previamente utilizados de STS.  Cuando está habilitada, la detección de la respuesta comprueba el token de la solicitud entrante y comprueba si el token se haya utilizado previamente.  Si el token se ya ha utilizado, se rechaza la solicitud y se produce una excepción de <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> .  
  
 Los pasos siguientes muestran los cambios de configuración necesarios para habilitar la detección de la respuesta.  
  
## Resumen de pasos  
  
-   Paso 1 \- cree una aplicación de formularios Web Forms sencillo ASP.NET y habilitar la detección de la respuesta  
  
-   Paso 2 \- pruebe la solución  
  
## Paso 1 \- cree una aplicación de formularios Web Forms sencillo ASP.NET y habilitar la detección de la respuesta  
 En este paso, creará una nueva aplicación de formularios Web Forms de ASP.NET y modificará *el archivo Web.config* para habilitar la detección de la respuesta.  
  
#### Para crear una aplicación ASP.NET simple  
  
1.  Inicie Visual Studio y haga clic en **Archivo**, **Nuevo**y, a continuación **Proyecto**.  
  
2.  En la ventana de **Nuevo proyecto** , haga clic en **Aplicación de formularios Web Forms de ASP.NET**.  
  
3.  En **Nombre**, entre en `TestApp` y presione **Aceptar**.  
  
4.  Haga clic con el botón secundario en el proyecto de **TestApp** en **Explorador de soluciones**, seleccione **identidad y Access**.  
  
5.  La ventana de **identidad y Access** aparece.  En **Proveedores**, seleccione **Pruebe la aplicación con el desarrollo local STS**, haga clic en **Aplicar**.  
  
6.  Agregue el siguiente elemento de **\<tokenReplayDetection\>** *al archivo de configuración Web.config* inmediatamente después de los elementos de **\<system.identityModel\>** y de **\<identityConfiguration\>** , como se muestra:  
  
    ```  
    <system.identityModel>  
        <identityConfiguration>  
            <tokenReplayDetection enabled=”true”/>  
    ```  
  
## Paso 2 \- pruebe la solución  
 En este paso, probará la aplicación WIF\- habilitada de ASP.NET para comprobar que se ha habilitado la detección de la respuesta.  
  
#### Para probar la aplicación WIF\- habilitada de ASP.NET para la detección de la respuesta  
  
1.  Ejecute la solución presionando la tecla de **F5** .  Debe mostrar con la página principal de ASP.NET y automáticamente autenticarse con el nombre de usuario *Terry*, que es el usuario predeterminado devuelto por el desarrollo STS.  
  
2.  Presione el botón de **Atrás** del explorador.  Debe mostrar con una página de **Error de servidor en la aplicación “\/”** con la descripción siguiente: *ID1062: la respuesta se ha detectado para: Token: 'System.IdentityModel.Tokens.SamlSecurityToken'*, seguido por un *AssertionId* y un *Emisor*  
  
     Hace referencia esta página de error porque una excepción de <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> tipo se produce cuando la respuesta del token se detectó.  Este error se produce porque intenta volver a enviar la solicitud inicial POST cuando el token se mostró por primera vez.  El botón de **Atrás** no producirá este comportamiento en solicitudes subsiguientes al servidor.