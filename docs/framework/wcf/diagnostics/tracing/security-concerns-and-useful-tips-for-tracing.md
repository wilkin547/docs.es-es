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
# <a name="security-concerns-and-useful-tips-for-tracing"></a><span data-ttu-id="f6cee-102">Riesgos de seguridad y sugerencias útiles para el seguimiento</span><span class="sxs-lookup"><span data-stu-id="f6cee-102">Security Concerns and Useful Tips for Tracing</span></span>
<span data-ttu-id="f6cee-103">Este tema describe cómo puede proteger información confidencial de ser expuesta, así como sugerencias útiles al utilizar WebHost.</span><span class="sxs-lookup"><span data-stu-id="f6cee-103">This topic describes how you can protect sensitive information from being exposed, as well as useful tips when using WebHost.</span></span>  
  
## <a name="using-a-custom-trace-listener-with-webhost"></a><span data-ttu-id="f6cee-104">Utilizar un agente de escucha de traza personalizado con WebHost</span><span class="sxs-lookup"><span data-stu-id="f6cee-104">Using a Custom Trace Listener with WebHost</span></span>  
 <span data-ttu-id="f6cee-105">Si está escribiendo su propio agente de escucha de traza, debe ser consciente de la posibilidad de que las trazas se puedan perder en el caso de un servicio hospedado en web.</span><span class="sxs-lookup"><span data-stu-id="f6cee-105">If you are writing your own trace listener, you should be aware of the possibility that traces might be lost in the case of a Web-hosted service.</span></span> <span data-ttu-id="f6cee-106">Cuando WebHost recicla, cierra el proceso activo mientras es sustituido por un duplicado.</span><span class="sxs-lookup"><span data-stu-id="f6cee-106">When WebHost recycles, it shuts down the live process while a duplicate takes over.</span></span> <span data-ttu-id="f6cee-107">Sin embargo, los dos procesos todavía deben tener acceso al mismo recurso durante algún tiempo, lo que depende del tipo de escucha.</span><span class="sxs-lookup"><span data-stu-id="f6cee-107">However, the two processes must still have access to the same resource for some time, which is dependent on the listener type.</span></span> <span data-ttu-id="f6cee-108">En este caso, `XmlWriterTraceListener` crea un nuevo archivo de seguimiento para el segundo proceso; mientras la traza de eventos de Windows administra varios procesos dentro de la misma sesión y da el acceso al mismo archivo.</span><span class="sxs-lookup"><span data-stu-id="f6cee-108">In this case, , `XmlWriterTraceListener` creates a new trace file for the second process; while Windows event tracing manages multiple processes within the same session and gives access to the same file.</span></span> <span data-ttu-id="f6cee-109">Si su propia escucha no proporciona funcionalidades similares, se pueden perder las trazas cuando el archivo es bloqueado por los dos procesos.</span><span class="sxs-lookup"><span data-stu-id="f6cee-109">If your own listener does not provide similar functionalities, traces can be lost when the file is locked up by the two processes.</span></span>  
  
 <span data-ttu-id="f6cee-110">También debe ser consciente de que un agente de escucha de traza personalizado puede enviar trazas y mensajes a través de la conexión, por ejemplo, a una base de datos remota.</span><span class="sxs-lookup"><span data-stu-id="f6cee-110">You should also be aware that a custom trace listener can send traces and messages on the wire, for example, to a remote database.</span></span> <span data-ttu-id="f6cee-111">Como un implementador de la aplicación, debería configurar las escuchas personalizadas con control de acceso adecuado.</span><span class="sxs-lookup"><span data-stu-id="f6cee-111">As an application deployer, you should configure custom listeners with appropriate access control.</span></span> <span data-ttu-id="f6cee-112">También debería aplicar el control de seguridad en cualquier información personal que se pueda exponer en la ubicación remota.</span><span class="sxs-lookup"><span data-stu-id="f6cee-112">You should also apply security control on any personal information that can be exposed at the remote location.</span></span>  
  
## <a name="logging-sensitive-information"></a><span data-ttu-id="f6cee-113">Registrar información confidencial</span><span class="sxs-lookup"><span data-stu-id="f6cee-113">Logging Sensitive Information</span></span>  
 <span data-ttu-id="f6cee-114">Las trazas contienen los encabezados del mensaje cuando un mensaje está en ámbito.</span><span class="sxs-lookup"><span data-stu-id="f6cee-114">Traces contain message headers when a message is in scope.</span></span> <span data-ttu-id="f6cee-115">Cuando las trazas están habilitadas, la información personal en encabezados específicos de la aplicación, como, una cadena de consulta; e información del cuerpo, como, un número de tarjeta de crédito, se puede volver visible en los registros.</span><span class="sxs-lookup"><span data-stu-id="f6cee-115">When tracing is enabled, personal information in application-specific headers, such as, a query string; and body information, such as, a credit card number, can become visible in the logs.</span></span> <span data-ttu-id="f6cee-116">El implementador de la aplicación es responsable para exigir el control de acceso en los archivos de seguimiento y configuración.</span><span class="sxs-lookup"><span data-stu-id="f6cee-116">The application deployer is responsible for enforcing access control on the configuration and trace files.</span></span> <span data-ttu-id="f6cee-117">Si no desea que este tipo de información sea visible, debería deshabilitar la traza o filtrar parte de los datos si desea compartir los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f6cee-117">If you do not want this kind of information to be visible, you should disable tracing, or filter out part of the data if you want to share the trace logs.</span></span>  
  
 <span data-ttu-id="f6cee-118">Las sugerencias siguientes pueden ayudarle a evitar que se exponga el contenido de un archivo de seguimiento involuntariamente:</span><span class="sxs-lookup"><span data-stu-id="f6cee-118">The following tips can help you to prevent the content of a trace file from being exposed unintentionally:</span></span>  
  
- <span data-ttu-id="f6cee-119">Asegúrese de que los archivos de registro estén protegidos mediante listas de control de acceso (ACL) tanto en WebHost y como en escenarios de host propio.</span><span class="sxs-lookup"><span data-stu-id="f6cee-119">Ensure that the log files are protected by Access Control Lists (ACL) both in WebHost and self-host scenarios.</span></span>  
  
- <span data-ttu-id="f6cee-120">Elija una extensión de archivo que no se pueda servir fácilmente utilizando una solicitud web.</span><span class="sxs-lookup"><span data-stu-id="f6cee-120">Choose a file extension that cannot be easily served using a Web request.</span></span> <span data-ttu-id="f6cee-121">Por ejemplo, la extensión de archivo .xml no es una opción segura.</span><span class="sxs-lookup"><span data-stu-id="f6cee-121">For example, the .xml file extension is not a safe choice.</span></span> <span data-ttu-id="f6cee-122">Puede comprobar la guía de administración de IIS para ver una lista de extensiones que se pueden servir.</span><span class="sxs-lookup"><span data-stu-id="f6cee-122">You can check the IIS administration guide to see a list of extensions that can be served.</span></span>  
  
- <span data-ttu-id="f6cee-123">Especifique una ruta de acceso absoluta para la ubicación del archivo de registro, que debería estar fuera del directorio público raíz de WebHost para evitar que una parte externa obtenga acceso utilizando un explorador web.</span><span class="sxs-lookup"><span data-stu-id="f6cee-123">Specify an absolute path for the log file location, which should be outside of the WebHost vroot public directory to prevent it from being accessed by an external party using a Web browser.</span></span>  
  
 <span data-ttu-id="f6cee-124">De forma predeterminada, las claves e información personal identificable (PII) como nombre de usuario y contraseña no están registradas en trazas y los mensajes registrados.</span><span class="sxs-lookup"><span data-stu-id="f6cee-124">By default, keys and personally identifiable information (PII) such as username and password are not logged in traces and logged messages.</span></span> <span data-ttu-id="f6cee-125">Sin embargo, un administrador del equipo puede utilizar el atributo `enableLoggingKnownPII` en el elemento `machineSettings` del archivo Machine.config para permitir que las aplicaciones que se ejecutan en el equipo registren información personal identificable (PII) conocida:</span><span class="sxs-lookup"><span data-stu-id="f6cee-125">A machine administrator, however, can use the `enableLoggingKnownPII` attribute in the `machineSettings` element of the Machine.config file to permit applications running on the machine to log known personally identifiable information (PII) as follows:</span></span>  
  
```xml  
<configuration>  
   <system.ServiceModel>  
      <machineSettings enableLoggingKnownPii="Boolean"/>  
   </system.ServiceModel>  
</configuration>
```  
  
 <span data-ttu-id="f6cee-126">Un implementador de aplicación puede utilizar el atributo `logKnownPii` en el archivo App.config o Web.config para permitir que PII se registre como sigue:</span><span class="sxs-lookup"><span data-stu-id="f6cee-126">An application deployer can then use the `logKnownPii` attribute in either the App.config or Web.config file to enable PII logging as follows:</span></span>  
  
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
  
 <span data-ttu-id="f6cee-127">Solo cuando ambos valores son `true` está habilitado el registro de PII.</span><span class="sxs-lookup"><span data-stu-id="f6cee-127">Only when both settings are `true` is PII logging enabled.</span></span> <span data-ttu-id="f6cee-128">La combinación de dos modificadores permite la flexibilidad de registrar la PII conocida para cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="f6cee-128">The combination of two switches allows the flexibility to log known PII for each application.</span></span>  
  
 <span data-ttu-id="f6cee-129">Debe ser consciente de que si especifica dos o más orígenes personalizados en un archivo de configuración, solo se leen los atributos del primer origen.</span><span class="sxs-lookup"><span data-stu-id="f6cee-129">You should be aware that if you specify two or more custom sources in a configuration file, only the attributes of the first source are read.</span></span> <span data-ttu-id="f6cee-130">Los otros se ignoran.</span><span class="sxs-lookup"><span data-stu-id="f6cee-130">The others are ignored.</span></span> <span data-ttu-id="f6cee-131">Esto significa que, para el archivo App.config siguiente, PII no se registra para ambos orígenes incluso aunque el registro de PII esté explícitamente habilitado para el segundo origen.</span><span class="sxs-lookup"><span data-stu-id="f6cee-131">This means that, for the following App.config, file, PII is not logged for both sources even though PII logging is explicitly enabled for the second source.</span></span>  
  
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
  
 <span data-ttu-id="f6cee-132">Si el elemento `<machineSettings enableLoggingKnownPii="Boolean"/>`<xref:System.Configuration.ConfigurationErrorsException> existe fuera del archivo Machine.config, el sistema inicia.</span><span class="sxs-lookup"><span data-stu-id="f6cee-132">If the `<machineSettings enableLoggingKnownPii="Boolean"/>` element exists outside the Machine.config file, the system throws a <xref:System.Configuration.ConfigurationErrorsException>.</span></span>  
  
 <span data-ttu-id="f6cee-133">Los cambios solo son efectivos cuando la aplicación se inicia o reinicia.</span><span class="sxs-lookup"><span data-stu-id="f6cee-133">The changes are effective only when the application starts or restarts.</span></span> <span data-ttu-id="f6cee-134">Un evento está registrado en el inicio cuando ambos atributos están establecidos en `true`.</span><span class="sxs-lookup"><span data-stu-id="f6cee-134">An event is logged at startup when both attributes are set to `true`.</span></span> <span data-ttu-id="f6cee-135">Un evento también está registrado si `logKnownPii` está establecido en `true` pero `enableLoggingKnownPii` es `false`.</span><span class="sxs-lookup"><span data-stu-id="f6cee-135">An event is also logged if `logKnownPii` is set to `true` but `enableLoggingKnownPii` is `false`.</span></span>  
  
 <span data-ttu-id="f6cee-136">Para obtener más información sobre el registro de PII, consulte Ejemplo de bloqueo de seguridad de [PII.](../../../../../docs/framework/wcf/samples/pii-security-lockdown.md)</span><span class="sxs-lookup"><span data-stu-id="f6cee-136">For more information on PII logging, see [PII Security Lockdown](../../../../../docs/framework/wcf/samples/pii-security-lockdown.md) sample.</span></span>  
  
 <span data-ttu-id="f6cee-137">El administrador del equipo e implementador de la aplicación debería ejercer una precaución extrema al utilizar estos dos modificadores.</span><span class="sxs-lookup"><span data-stu-id="f6cee-137">The machine administrator and application deployer should exercise extreme caution when using these two switches.</span></span> <span data-ttu-id="f6cee-138">Si el registro de PII está habilitado, las claves de seguridad y PII están registradas.</span><span class="sxs-lookup"><span data-stu-id="f6cee-138">If PII logging is enabled, security keys and PII are logged.</span></span> <span data-ttu-id="f6cee-139">Si está deshabilitado, los datos sensibles y específicos de la aplicación todavía están registrados en encabezados del mensaje y cuerpos.</span><span class="sxs-lookup"><span data-stu-id="f6cee-139">If it is disabled, sensitive and application-specific data is still logged in message headers and bodies.</span></span> <span data-ttu-id="f6cee-140">Para obtener una discusión más detallada sobre la privacidad y la protección de la PII para que no se exponga, consulte Privacidad del [usuario](https://docs.microsoft.com/previous-versions/dotnet/articles/aa480490(v=msdn.10)).</span><span class="sxs-lookup"><span data-stu-id="f6cee-140">For a more thorough discussion on privacy and protecting PII from being exposed, see [User Privacy](https://docs.microsoft.com/previous-versions/dotnet/articles/aa480490(v=msdn.10)).</span></span>  
  
 <span data-ttu-id="f6cee-141">Además, la dirección IP del remitente del mensaje se registra una vez por conexión para transportes orientados a la conexión y una vez por mensaje enviado de otro modo.</span><span class="sxs-lookup"><span data-stu-id="f6cee-141">In addition, the IP address of the message sender is logged once per connection for connection-oriented transports, and once per message sent otherwise.</span></span> <span data-ttu-id="f6cee-142">Esto se hace sin el consentimiento del remitente.</span><span class="sxs-lookup"><span data-stu-id="f6cee-142">This is done without the consent of the sender.</span></span> <span data-ttu-id="f6cee-143">Sin embargo, este registro solo se produce en los niveles de traza Información o Detallado, que no son los niveles de traza predeterminados o recomendados en la producción, salvo para la depuración activa.</span><span class="sxs-lookup"><span data-stu-id="f6cee-143">However, this logging only occurs at the Information or Verbose tracing levels, which are not the default or recommended tracing levels in production, except for live debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6cee-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f6cee-144">See also</span></span>

- [<span data-ttu-id="f6cee-145">Rastreo</span><span class="sxs-lookup"><span data-stu-id="f6cee-145">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
