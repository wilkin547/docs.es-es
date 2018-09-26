---
title: 'Cómo: habilitar el seguimiento de WIF'
ms.date: 03/30/2017
ms.assetid: 271b6889-3454-46ff-96ab-9feb15e742ee
author: BrucePerlerMS
ms.openlocfilehash: f763c279c29bec73d4fc20d59dc86726d84e21bd
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47171704"
---
# <a name="how-to-enable-wif-tracing"></a>Cómo: habilitar el seguimiento de WIF
## <a name="applies-to"></a>Se aplica a  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   Formularios Web Forms ASP.NET®  
  
## <a name="summary"></a>Resumen  
 En este tema de procedimientos se proporcionan los procedimientos paso a paso detallados para habilitar el seguimiento de WIF en una aplicación ASP.NET. También se proporcionan instrucciones de prueba de la aplicación para comprobar que el registro y el agente de escucha de seguimiento funcionan correctamente. Esta sección de procedimientos no tiene instrucciones detalladas para crear un servicio de token de seguridad (STS) y en su lugar se utiliza el STS de desarrollo que se incluye con la extensión Identity and Access Tool. El STS de desarrollo no realiza la autenticación real y está pensado únicamente para pruebas. Para completar este procedimiento, tendrá que instalar la extensión Identity and Access Tool. Se puede descargar en la siguiente ubicación: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849).  
  
> [!IMPORTANT]
>  Habilitar la traza de WIF para aplicaciones pasivas, es decir, aplicaciones que utilizan el protocolo de WS-Federation, podría exponer la aplicación a ataques de denegación de servicio (DoS) o a la divulgación de información a terceros malintencionados. Esto incluye tanto RP pasivos como STS pasivos. Por este motivo, es recomendable que no habilite el seguimiento de WIF para RP o STS pasivos en un entorno de producción.  
  
## <a name="contents"></a>Contenido  
  
-   Objetivos  
  
-   Información general  
  
-   Resumen de pasos  
  
-   Paso 1 - Crear una aplicación de formularios Web Forms ASP.NET simple y habilitar el seguimiento  
  
-   Paso 2 – Probar la solución  
  
## <a name="objectives"></a>Objetivos  
  
-   Crear una aplicación ASP.NET simple que use WIF y el STS de desarrollo desde la herramienta Identity and Access Tool  
  
-   Habilitar el seguimiento y comprobar que funciona  
  
## <a name="overview"></a>Información general  
 El seguimiento permite depurar y solucionar muchos tipos de problemas con WIF, como tokens, cookies, notificaciones, mensajes de protocolo, etc. El seguimiento de WIF es similar al seguimiento de WCF; por ejemplo, puede elegir el nivel de detalle de los seguimientos para mostrar cualquier tipo de mensaje, desde mensajes críticos a todos los mensajes. Los seguimientos de WIF se pueden generar en archivos **.xml** o en archivos **.svclog** que se pueden consultar mediante la herramienta Visor de seguimiento de servicios. Esta herramienta se encuentra en el directorio **bin** de la ruta de instalación de Windows SDK del equipo, por ejemplo: **C:\Archivos de programa\Microsoft SDKs\Windows\v7.1\Bin\SvcTraceViewer.exe**.  
  
## <a name="summary-of-steps"></a>Resumen de pasos  
  
-   Paso 1 - Crear una aplicación de formularios Web Forms ASP.NET simple y habilitar el seguimiento  
  
-   Paso 2 – Probar la solución  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application-and-enable-tracing"></a>Paso 1 - Crear una aplicación de formularios Web Forms ASP.NET simple y habilitar el seguimiento  
 En este paso, creará una aplicación de formularios Web Forms de ASP.NET y modificará el archivo *Web.config* para habilitar el seguimiento.  
  
#### <a name="to-create-a-simple-aspnet-application"></a>Para crear una aplicación de ASP.NET sencilla  
  
1.  Inicie Visual Studio y haga clic en **Archivo**, **Nuevo** y, luego, en **Proyecto**.  
  
2.  En la ventana **Nuevo proyecto**, haga clic en **Aplicación de formularios Web Forms ASP.NET**.  
  
3.  En **Nombre**, escriba `TestApp` y haga clic en **Aceptar**.  
  
4.  Haga clic con el botón derecho en el proyecto **TestApp** en el **Explorador de soluciones** y seleccione **Identity and Access**.  
  
5.  Aparecerá la ventana **Identity and Access**. En **Proveedores**, seleccione **Test your application with the Local Development STS** (Probar la aplicación con el STS de desarrollo local) y haga clic en **Aplicar**.  
  
6.  Cree una carpeta con el nombre **logs** en la raíz de la unidad **C:**, de la siguiente manera: **C:\logs**.  
  
7.  Agregue el siguiente elemento **\<system.diagnostics>** al archivo de configuración *Web.config* inmediatamente después del elemento **\</configSections>** de cierre, de la siguiente manera:  
  
    ```xml  
    <configuration>  
        <configSections>  
        …  
        </configSections>  
        <system.diagnostics>  
            <sources>  
                <source name="System.IdentityModel" switchValue="Verbose">  
                    <listeners>  
                        <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="C:\logs\WIF.xml" />  
                    </listeners>  
                </source>  
            </sources>  
            <trace autoflush="true" />  
        </system.diagnostics>  
    ```  
  
    > [!NOTE]
    >  La ubicación del directorio especificado en el atributo **initializeData** debe existir antes de que pueda comenzar el registro. Si no existe la ubicación, no se creará ningún registro.  
  
     Las opciones de configuración anteriores habilitarán el seguimiento **Detallado** para WIF y guardarán el registro resultante en el archivo **C:\logs\WIF.xml**.  
  
## <a name="step-2--test-your-solution"></a>Paso 2 – Probar la solución  
 En este paso, probará la aplicación ASP.NET habilitada con WIF para comprobar que los registros se están grabando.  
  
#### <a name="to-test-your-wif-enabled-aspnet-application-for-successful-tracing"></a>Para probar la aplicación ASP.NET habilitada con WIF para un seguimiento correcto  
  
1.  Presione la tecla **F5** para ejecutar la solución. Debe aparecer la página principal de ASP.NET predeterminada y se le debe autenticar automáticamente con el nombre de usuario *Terry*, que es el usuario predeterminado devuelto por el STS de desarrollo.  
  
2.  Cierre la ventana del explorador y después desplácese hasta la carpeta **C:\logs**. Abra el archivo **C:\logs\WIF.xml** mediante un editor de texto.  
  
3.  Inspeccione el archivo **WIF.xml** y compruebe que contiene entradas que comienzan por **\<E2ETraceEvent>**. Estos seguimientos contendrán elementos **\<TraceRecord>** con descripciones de la actividad objeto de seguimiento, como **Validación de SecurityToken**.
