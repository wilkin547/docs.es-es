---
title: Riesgos de seguridad y sugerencias útiles para el seguimiento
ms.date: 03/30/2017
ms.assetid: 88bc2880-ecb9-47cd-9816-39016a07076f
ms.openlocfilehash: 5ced4f3a3a5e83564703db88b28ee2b3c6eeb1a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185718"
---
# <a name="security-concerns-and-useful-tips-for-tracing"></a>Riesgos de seguridad y sugerencias útiles para el seguimiento
Este tema describe cómo puede proteger información confidencial de ser expuesta, así como sugerencias útiles al utilizar WebHost.  
  
## <a name="using-a-custom-trace-listener-with-webhost"></a>Utilizar un agente de escucha de traza personalizado con WebHost  
 Si está escribiendo su propio agente de escucha de traza, debe ser consciente de la posibilidad de que las trazas se puedan perder en el caso de un servicio hospedado en web. Cuando WebHost recicla, cierra el proceso activo mientras es sustituido por un duplicado. Sin embargo, los dos procesos todavía deben tener acceso al mismo recurso durante algún tiempo, lo que depende del tipo de escucha. En este caso, `XmlWriterTraceListener` crea un nuevo archivo de seguimiento para el segundo proceso; mientras la traza de eventos de Windows administra varios procesos dentro de la misma sesión y da el acceso al mismo archivo. Si su propia escucha no proporciona funcionalidades similares, se pueden perder las trazas cuando el archivo es bloqueado por los dos procesos.  
  
 También debe ser consciente de que un agente de escucha de traza personalizado puede enviar trazas y mensajes a través de la conexión, por ejemplo, a una base de datos remota. Como un implementador de la aplicación, debería configurar las escuchas personalizadas con control de acceso adecuado. También debería aplicar el control de seguridad en cualquier información personal que se pueda exponer en la ubicación remota.  
  
## <a name="logging-sensitive-information"></a>Registrar información confidencial  
 Las trazas contienen los encabezados del mensaje cuando un mensaje está en ámbito. Cuando las trazas están habilitadas, la información personal en encabezados específicos de la aplicación, como, una cadena de consulta; e información del cuerpo, como, un número de tarjeta de crédito, se puede volver visible en los registros. El implementador de la aplicación es responsable para exigir el control de acceso en los archivos de seguimiento y configuración. Si no desea que este tipo de información sea visible, debería deshabilitar la traza o filtrar parte de los datos si desea compartir los registros de seguimiento.  
  
 Las sugerencias siguientes pueden ayudarle a evitar que se exponga el contenido de un archivo de seguimiento involuntariamente:  
  
- Asegúrese de que los archivos de registro estén protegidos mediante listas de control de acceso (ACL) tanto en WebHost y como en escenarios de host propio.  
  
- Elija una extensión de archivo que no se pueda servir fácilmente utilizando una solicitud web. Por ejemplo, la extensión de archivo .xml no es una opción segura. Puede comprobar la guía de administración de IIS para ver una lista de extensiones que se pueden servir.  
  
- Especifique una ruta de acceso absoluta para la ubicación del archivo de registro, que debería estar fuera del directorio público raíz de WebHost para evitar que una parte externa obtenga acceso utilizando un explorador web.  
  
 De forma predeterminada, las claves e información personal identificable (PII) como nombre de usuario y contraseña no están registradas en trazas y los mensajes registrados. Sin embargo, un administrador del equipo puede utilizar el atributo `enableLoggingKnownPII` en el elemento `machineSettings` del archivo Machine.config para permitir que las aplicaciones que se ejecutan en el equipo registren información personal identificable (PII) conocida:  
  
```xml  
<configuration>  
   <system.ServiceModel>  
      <machineSettings enableLoggingKnownPii="Boolean"/>  
   </system.ServiceModel>  
</configuration>
```  
  
 Un implementador de aplicación puede utilizar el atributo `logKnownPii` en el archivo App.config o Web.config para permitir que PII se registre como sigue:  
  
```xml  
<system.diagnostics>  
  <sources>  
      <source name="System.ServiceModel.MessageLogging"  
        logKnownPii="true">  
        <listeners>  
                 <add name="messages"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="c:\logs\messages.svclog" />  
          </listeners>  
      </source>  
  </sources>  
</system.diagnostics>  
```  
  
 Solo cuando ambos valores son `true` está habilitado el registro de PII. La combinación de dos modificadores permite la flexibilidad de registrar la PII conocida para cada aplicación.  
  
 Debe ser consciente de que si especifica dos o más orígenes personalizados en un archivo de configuración, solo se leen los atributos del primer origen. Los otros se ignoran. Esto significa que, para el archivo App.config siguiente, PII no se registra para ambos orígenes incluso aunque el registro de PII esté explícitamente habilitado para el segundo origen.  
  
```xml  
<system.diagnostics>  
  <sources>  
      <source name="System.ServiceModel.MessageLogging"  
        logKnownPii="false">  
        <listeners>  
           <add name="messages"  
                type="System.Diagnostics.XmlWriterTraceListener"  
                initializeData="c:\logs\messages.svclog" />  
          </listeners>  
      </source>  
      <source name="System.ServiceModel"
         logKnownPii="true">  
         <listeners>  
            <add name="xml" />  
         </listeners>  
      </source>  
  </sources>  
</system.diagnostics>  
```  
  
 Si el elemento `<machineSettings enableLoggingKnownPii="Boolean"/>`<xref:System.Configuration.ConfigurationErrorsException> existe fuera del archivo Machine.config, el sistema inicia.  
  
 Los cambios solo son efectivos cuando la aplicación se inicia o reinicia. Un evento está registrado en el inicio cuando ambos atributos están establecidos en `true`. Un evento también está registrado si `logKnownPii` está establecido en `true` pero `enableLoggingKnownPii` es `false`.  
  
 Para obtener más información sobre el registro de PII, consulte Ejemplo de bloqueo de seguridad de [PII.](../../../../../docs/framework/wcf/samples/pii-security-lockdown.md)  
  
 El administrador del equipo e implementador de la aplicación debería ejercer una precaución extrema al utilizar estos dos modificadores. Si el registro de PII está habilitado, las claves de seguridad y PII están registradas. Si está deshabilitado, los datos sensibles y específicos de la aplicación todavía están registrados en encabezados del mensaje y cuerpos. Para obtener una discusión más detallada sobre la privacidad y la protección de la PII para que no se exponga, consulte Privacidad del [usuario](https://docs.microsoft.com/previous-versions/dotnet/articles/aa480490(v=msdn.10)).  
  
 Además, la dirección IP del remitente del mensaje se registra una vez por conexión para transportes orientados a la conexión y una vez por mensaje enviado de otro modo. Esto se hace sin el consentimiento del remitente. Sin embargo, este registro solo se produce en los niveles de traza Información o Detallado, que no son los niveles de traza predeterminados o recomendados en la producción, salvo para la depuración activa.  
  
## <a name="see-also"></a>Consulte también

- [Rastreo](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
