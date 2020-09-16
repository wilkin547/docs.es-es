---
title: Riesgos de seguridad y sugerencias útiles para el seguimiento
ms.date: 03/30/2017
ms.assetid: 88bc2880-ecb9-47cd-9816-39016a07076f
ms.openlocfilehash: 91a1b4bab3ac47f41821ad69228310c3993cf037
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555047"
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
  
 Para obtener más información sobre el registro de PII, vea ejemplo de [bloqueo de seguridad de PII](../../samples/pii-security-lockdown.md) .  
  
 El administrador del equipo e implementador de la aplicación debería ejercer una precaución extrema al utilizar estos dos modificadores. Si el registro de PII está habilitado, las claves de seguridad y PII están registradas. Si está deshabilitado, los datos sensibles y específicos de la aplicación todavía están registrados en encabezados del mensaje y cuerpos. Para obtener una explicación más detallada sobre la privacidad y la protección de PII, vea privacidad de los [usuarios](/previous-versions/dotnet/articles/aa480490(v=msdn.10)).  
  
 Además, la dirección IP del remitente del mensaje se registra una vez por conexión para transportes orientados a la conexión y una vez por mensaje enviado de otro modo. Esto se hace sin el consentimiento del remitente. Sin embargo, este registro solo se produce en los niveles de traza Información o Detallado, que no son los niveles de traza predeterminados o recomendados en la producción, salvo para la depuración activa.  
  
## <a name="see-also"></a>Vea también

- [Seguimiento](index.md)
