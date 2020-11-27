---
title: Riesgos de seguridad relativos al registro de mensajes
ms.date: 03/30/2017
ms.assetid: 21f513f2-815b-47f3-85a6-03c008510038
ms.openlocfilehash: 8594329fb27aa1d77a2baffee2a7e37ea0d009c4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96283775"
---
# <a name="security-concerns-for-message-logging"></a>Riesgos de seguridad relativos al registro de mensajes

En este tema se describe cómo puede proteger los datos confidenciales para que no se expongan en registros de mensajes, así como los eventos generados por el registro de mensajes.  
  
## <a name="security-concerns"></a>Cuestiones de seguridad  
  
### <a name="logging-sensitive-information"></a>Registrar información confidencial  

 Windows Communication Foundation (WCF) no modifica ningún dato en los encabezados y el cuerpo específicos de la aplicación. WCF tampoco realiza un seguimiento de la información personal en encabezados específicos de la aplicación o en datos de cuerpo.  
  
 Cuando el registro de mensajes está habilitado, la información personal en encabezados específicos de la aplicación, como una cadena de consulta; e información del cuerpo, como un número de tarjeta de crédito, se puede volver visible en los registros. El implementador de la aplicación es el responsable de exigir el control de acceso en los archivos de registro y configuración. Si no desea que este tipo de información sea visible, debería deshabilitar el registro o filtrar parte de los datos si desea compartir los registros.  
  
 Las sugerencias siguientes pueden ayudarle a evitar que se exponga el contenido de un archivo de registro involuntariamente:  
  
- Asegúrese de que los archivos de registro estén protegidos mediante listas de control de acceso (ACL) tanto en host de web y como en escenarios de host propio.  
  
- Elija una extensión de archivo que no se pueda servir fácilmente utilizando una solicitud web. Por ejemplo, la extensión de archivo .xml no es una opción segura. Puede comprobar la guía de administración de Internet Information Services (IIS) para ver una lista de extensiones que se pueden servir.  
  
- Especifique una ruta de acceso absoluta para la ubicación del archivo de registro, que debería estar fuera del directorio público raíz de Web host para evitar que una parte externa obtenga acceso utilizando un explorador web.  
  
 De forma predeterminada, las claves e información personal identificable (PII) como nombre de usuario y contraseña no están registradas en trazas y los mensajes registrados. Sin embargo, un administrador del equipo puede utilizar el atributo `enableLoggingKnownPII` en el elemento `machineSettings` del archivo Machine.config para permitir que las aplicaciones que se ejecutan en el equipo registren información personal identificable (PII) conocida. La siguiente configuración muestra cómo realizar esto:  
  
```xml  
<configuration>  
   <system.serviceModel>  
      <machineSettings enableLoggingKnownPii="true"/>  
   </system.serviceModel>  
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
  
> [!IMPORTANT]
> En [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] las marcas `logEntireMessage` y `logKnownPii` también se deben establecer en `true` en el archivo Web.config o en el archivo App.config para habilitar el registro de PII, como se muestra en el siguiente ejemplo `<system.serviceModel><messageLogging logEntireMessage="true" logKnownPii="true" …`.  
  
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
                 <add name="traces"  
                      type="System.Diagnostics.XmlWriterTraceListener"  
                      initializeData="c:\logs\traces.svclog" />  
              </listeners>  
      </source>  
   </sources>  
</system.diagnostics>  
```  
  
 Si el elemento `<machineSettings enableLoggingKnownPii="Boolean"/>`<xref:System.Configuration.ConfigurationErrorsException> existe fuera del archivo Machine.config, el sistema inicia.  
  
 Los cambios solo son efectivos cuando la aplicación se inicia o reinicia. Un evento está registrado en el inicio cuando ambos atributos están establecidos en `true`. Un evento también está registrado si `logKnownPii` está establecido en `true` pero `enableLoggingKnownPii` es `false`.  
  
 El administrador del equipo e implementador de la aplicación debería ejercer una precaución extrema al utilizar estos dos modificadores. Si el registro de PII está habilitado, las claves de seguridad y PII están registradas. Si está deshabilitado, los datos sensibles y específicos de la aplicación todavía están registrados en encabezados del mensaje y cuerpos. Para obtener una explicación más detallada sobre la privacidad y la protección de PII, vea privacidad de los [usuarios](/previous-versions/dotnet/articles/aa480490(v=msdn.10)).  
  
> [!CAUTION]
> PII no se oculta en mensajes incorrectos. Tales mensajes se registran tal cual sin ninguna modificación. Los atributos mencionados previamente no tienen ningún efecto sobre esto.  
  
### <a name="custom-trace-listener"></a>Agente de escucha de traza personalizado  

 Agregar un agente de escucha de traza personalizado en el origen de traza del registro de mensajes es un privilegio que debe estar restringido al administrador. Esto se debe a que los agentes de escucha personalizados malintencionados se pueden configurar para enviar mensajes remotamente, lo que conduce a la divulgación de información confidencial. Además, si configura un agente de escucha personalizado para enviar mensajes en la conexión, como, por ejemplo, a una base de datos remota, debería exigir un control de acceso apropiado en los registros de mensajes en el equipo remoto.  
  
## <a name="events-triggered-by-message-logging"></a>Eventos activados mediante el registro de mensajes  

 La siguiente es una lista de todos los eventos emitidos por el registro de mensajes.  
  
- Registro de mensajes activado: se emite este evento cuando el registro de mensajes está habilitado en la configuración o a través de WMI. El contenido del evento es “Se ha activado el registro de mensajes. Puede que se registre información confidencial en texto no cifrado, incluso aunque estuviesen cifrados en la conexión, por ejemplo, los cuerpos de mensajes”.  
  
- Registro de mensajes desactivado: se emite este evento cuando el registro de mensajes se deshabilita a través de WMI. El contenido del evento es “Se ha desactivado el registro de mensajes”.  
  
- Registro PII conocido activado: se emite este evento cuando el registro de PII conocido está habilitado. Esto sucede cuando el `enableLoggingKnownPii` atributo del `machineSettings` elemento del Machine.config archivo se establece en `true` y el `logKnownPii` atributo del `source` elemento en el archivo App.config o Web.config está establecido en `true` .  
  
- Registro de PII conocido no permitido: se emite este evento cuando no se permite el registro de PII conocido. Esto sucede cuando el `logKnownPii` atributo del `source` elemento en el archivo App.config o Web.config está establecido en `true` , pero el atributo del `enableLoggingKnownPii` `machineSettings` elemento del archivo Machine.config está establecido en `false` . No se inicia ninguna excepción.  
  
 Estos eventos se pueden ver en la herramienta Visor de eventos que viene con Windows. Para obtener más información sobre esto, vea [registro de eventos](./event-logging/index.md).  
  
## <a name="see-also"></a>Vea también

- [Registro de mensajes](message-logging.md)
- [Riesgos de seguridad y sugerencias útiles para el seguimiento](./tracing/security-concerns-and-useful-tips-for-tracing.md)
