---
title: Información de privacidad de Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, privacy information
- WCF, privacy information
- privacy information [WCF]
ms.assetid: c9553724-f3e7-45cb-9ea5-450a22d309d9
ms.openlocfilehash: f909b987da31a0a4af605d603d1c7b7a35615f19
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2019
ms.locfileid: "56333409"
---
# <a name="windows-communication-foundation-privacy-information"></a><span data-ttu-id="401ff-102">Información de privacidad de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="401ff-102">Windows Communication Foundation Privacy Information</span></span>
<span data-ttu-id="401ff-103">Microsoft se compromete a proteger la privacidad de usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="401ff-103">Microsoft is committed to protecting end-users' privacy.</span></span> <span data-ttu-id="401ff-104">Al compilar una aplicación mediante Windows Communication Foundation (WCF), versión 3.0, la aplicación puede afectar la privacidad de sus usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="401ff-104">When you build an application using Windows Communication Foundation (WCF), version 3.0, your application may impact your end-users' privacy.</span></span> <span data-ttu-id="401ff-105">Por ejemplo, su aplicación puede recoger explícitamente información de contacto del usuario o puede solicitar o enviar información a través de Internet a su sitio web.</span><span class="sxs-lookup"><span data-stu-id="401ff-105">For example, your application may explicitly collect user contact information, or it may request or send information over the Internet to your Web site.</span></span> <span data-ttu-id="401ff-106">Si incrusta la tecnología de Microsoft en su aplicación, esa tecnología puede tener su propio comportamiento que podría afectar a la privacidad.</span><span class="sxs-lookup"><span data-stu-id="401ff-106">If you embed Microsoft technology in your application, that technology may have its own behavior that might affect privacy.</span></span> <span data-ttu-id="401ff-107">WCF no envía ninguna información a Microsoft desde su aplicación a menos que usted o el usuario final elija enviarla.</span><span class="sxs-lookup"><span data-stu-id="401ff-107">WCF does not send any information to Microsoft from your application unless you or the end-user choose to send it to us.</span></span>  
  
## <a name="wcf-in-brief"></a><span data-ttu-id="401ff-108">WCF en breve</span><span class="sxs-lookup"><span data-stu-id="401ff-108">WCF in Brief</span></span>  
 <span data-ttu-id="401ff-109">WCF es un marco de mensajería distribuido mediante Microsoft .NET Framework que permite a los desarrolladores crear aplicaciones distribuidas.</span><span class="sxs-lookup"><span data-stu-id="401ff-109">WCF is a distributed messaging framework using the Microsoft .NET Framework that allows developers to build distributed applications.</span></span> <span data-ttu-id="401ff-110">Los mensajes comunicados entre dos aplicaciones contienen encabezado e información del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="401ff-110">Messages communicated between two applications contain header and body information.</span></span>  
  
 <span data-ttu-id="401ff-111">Los encabezados pueden contener enrutamiento de mensajes, información de seguridad, transacciones, y más, en función de los servicios utilizados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="401ff-111">Headers may contain message routing, security information, transactions, and more depending on the services used by the application.</span></span> <span data-ttu-id="401ff-112">Generalmente, se cifran los mensajes de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="401ff-112">Messages are typically encrypted by default.</span></span> <span data-ttu-id="401ff-113">Una excepción es cuando se utiliza `BasicHttpBinding`, diseñado para el uso con Servicio Web no seguros, heredados.</span><span class="sxs-lookup"><span data-stu-id="401ff-113">The one exception is when using the `BasicHttpBinding`, which was designed for use with non-secured, legacy Web services.</span></span> <span data-ttu-id="401ff-114">Como diseñador de aplicaciones, es el responsable del último diseño.</span><span class="sxs-lookup"><span data-stu-id="401ff-114">As the application designer, you are responsible for the final design.</span></span> <span data-ttu-id="401ff-115">Los mensajes en el cuerpo SOAP contienen datos específicos de la aplicación; Sin embargo, estos datos, como la información personal definido por la aplicación, se pueden proteger mediante el uso de características de cifrado o la confidencialidad de WCF.</span><span class="sxs-lookup"><span data-stu-id="401ff-115">Messages in the SOAP body contain application-specific data; however, this data, such as application-defined personal information, can be secured by using WCF encryption or confidentiality features.</span></span> <span data-ttu-id="401ff-116">Las secciones siguientes describen las características que pueden afectan a la privacidad.</span><span class="sxs-lookup"><span data-stu-id="401ff-116">The following sections describe the features that potentially impact privacy.</span></span>  
  
## <a name="messaging"></a><span data-ttu-id="401ff-117">Mensajería</span><span class="sxs-lookup"><span data-stu-id="401ff-117">Messaging</span></span>  
 <span data-ttu-id="401ff-118">Cada mensaje WCF tiene un encabezado de dirección que especifica el destino del mensaje y donde debería ir la respuesta.</span><span class="sxs-lookup"><span data-stu-id="401ff-118">Each WCF message has an address header that specifies the message destination and where the reply should go.</span></span>  
  
 <span data-ttu-id="401ff-119">El componente de dirección de una dirección de extremo es un Identificador uniforme de recursos (URI) que identifica el extremo.</span><span class="sxs-lookup"><span data-stu-id="401ff-119">The address component of an endpoint address is a Uniform Resource Identifier (URI) that identifies the endpoint.</span></span> <span data-ttu-id="401ff-120">La dirección puede ser una dirección de red o una dirección lógica.</span><span class="sxs-lookup"><span data-stu-id="401ff-120">The address can be a network address or a logical address.</span></span> <span data-ttu-id="401ff-121">La dirección puede incluir nombre del equipo (nombre del host, nombre de dominio completo) y una dirección IP.</span><span class="sxs-lookup"><span data-stu-id="401ff-121">The address may include machine name (hostname, fully qualified domain name) and an IP address.</span></span> <span data-ttu-id="401ff-122">La dirección del extremo también puede contener un identificador único global (GUID) o una colección de GUID para el direccionamiento temporal utilizado para discernir cada dirección.</span><span class="sxs-lookup"><span data-stu-id="401ff-122">The endpoint address may also contain a globally unique identifier (GUID), or a collection of GUIDs for temporary addressing used to discern each address.</span></span> <span data-ttu-id="401ff-123">Cada mensaje contiene un id. de mensaje que es un GUID.</span><span class="sxs-lookup"><span data-stu-id="401ff-123">Each message contains a message ID that is a GUID.</span></span> <span data-ttu-id="401ff-124">Esta característica sigue la regla de referencia WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="401ff-124">This feature follows the WS-Addressing reference standard.</span></span>  
  
 <span data-ttu-id="401ff-125">La capa de mensajería de WCF no escribe información personal en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="401ff-125">The WCF messaging layer does not write any personal information to the local machine.</span></span> <span data-ttu-id="401ff-126">Sin embargo, podría propagar información personal en el nivel de la red si un programador del servicio ha creado un servicio que expone dicha información (por ejemplo, utilizando el nombre de una persona en un nombre de extremo o incluso información personal en el Lenguaje de descripción de servicios Web (WSDL) del extremo pero no requiero que los clientes utilicen http para tener acceso al WSDL).</span><span class="sxs-lookup"><span data-stu-id="401ff-126">However, it might propagate personal information at the network level if a service developer has created a service that exposes such information (for example, by using a person's name in an endpoint name, or including personal information in the endpoint's Web Services Description Language but not requiring clients to use https to access the WSDL).</span></span> <span data-ttu-id="401ff-127">Además, si un programador ejecuta la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) herramienta contra un extremo que expone información personal, la salida podría contener esa información y el archivo de salida se escribe en el disco duro local.</span><span class="sxs-lookup"><span data-stu-id="401ff-127">Also, if a developer runs the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool against an endpoint that exposes personal information, the tool's output could contain that information, and the output file is written to the local hard disk.</span></span>  
  
## <a name="hosting"></a><span data-ttu-id="401ff-128">Hospedaje</span><span class="sxs-lookup"><span data-stu-id="401ff-128">Hosting</span></span>  
 <span data-ttu-id="401ff-129">La característica de hospedaje de WCF permite a las aplicaciones para iniciarse a petición o para habilitar el uso compartido de puertos entre varias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="401ff-129">The hosting feature in WCF allows applications to start on demand or to enable port sharing between multiple applications.</span></span> <span data-ttu-id="401ff-130">Una aplicación de WCF puede hospedarse en Internet Information Services (IIS), similar a [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="401ff-130">An WCF application can be hosted in Internet Information Services (IIS), similar to [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].</span></span>  
  
 <span data-ttu-id="401ff-131">Al hospedarse, no se expone ninguna información específica sobre la red y no mantiene los datos en el equipo.</span><span class="sxs-lookup"><span data-stu-id="401ff-131">Hosting does not expose any specific information on the network and it does not keep data on the machine.</span></span>  
  
## <a name="message-security"></a><span data-ttu-id="401ff-132">Seguridad de los mensajes</span><span class="sxs-lookup"><span data-stu-id="401ff-132">Message Security</span></span>  
 <span data-ttu-id="401ff-133">Seguridad de WCF proporciona las capacidades de seguridad para aplicaciones de mensajería.</span><span class="sxs-lookup"><span data-stu-id="401ff-133">WCF security provides the security capabilities for messaging applications.</span></span> <span data-ttu-id="401ff-134">Las funciones de seguridad proporcionadas incluyen autenticación y autorización.</span><span class="sxs-lookup"><span data-stu-id="401ff-134">The security functions provided include authentication and authorization.</span></span>  
  
 <span data-ttu-id="401ff-135">La autenticación se lleva a cabo pasando las credenciales entre clientes y servicios.</span><span class="sxs-lookup"><span data-stu-id="401ff-135">Authentication is performed by passing credentials between the clients and services.</span></span> <span data-ttu-id="401ff-136">La autenticación se puede llevar a cabo a través de la seguridad de nivel de transporte o a través de seguridad del nivel del mensaje SOAP, tal y como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="401ff-136">Authentication can be either through transport-level security or through SOAP message-level security, as follows:</span></span>  
  
-   <span data-ttu-id="401ff-137">En seguridad del mensaje SOAP, la autenticación se realiza a través de las credenciales como el nombre de usuario/contraseñas, certificados X.509, vales de Kerberos y tokens de SAML, los cuales podrían contener datos personales, en función del emisor.</span><span class="sxs-lookup"><span data-stu-id="401ff-137">In SOAP message security, authentication is performed through credentials like username/passwords, X.509 certificates, Kerberos tickets, and SAML tokens, all of which might contain personal information, depending on the issuer.</span></span>  
  
-   <span data-ttu-id="401ff-138">En el uso de seguridad de transporte, la autenticación se realiza a través de los mecanismos de autenticación de transporte tradicionales como los esquemas de autenticación de HTTP (Básica, implícita, Negociada, Autorización de Windows Integrada, NTLM, Ninguna, y Anónima) y autenticación de formularios.</span><span class="sxs-lookup"><span data-stu-id="401ff-138">Using transport security, authentication is done through traditional transport authentication mechanisms like HTTP authentication schemes (Basic, Digest, Negotiate, Integrated Windows Authorization, NTLM, None, and Anonymous), and form authentication.</span></span>  
  
 <span data-ttu-id="401ff-139">La autenticación puede producir una sesión segura establecida entre los extremos en comunicación.</span><span class="sxs-lookup"><span data-stu-id="401ff-139">Authentication can result in a secure session established between the communicating endpoints.</span></span> <span data-ttu-id="401ff-140">Un GUID, cuya duración es igual a la sesión de seguridad, identifica la sesión.</span><span class="sxs-lookup"><span data-stu-id="401ff-140">The session is identified by a GUID that lasts the lifetime of the security session.</span></span> <span data-ttu-id="401ff-141">La tabla siguiente muestra lo que se guarda y dónde.</span><span class="sxs-lookup"><span data-stu-id="401ff-141">The following table shows what is kept and where.</span></span>  
  
|<span data-ttu-id="401ff-142">Datos</span><span class="sxs-lookup"><span data-stu-id="401ff-142">Data</span></span>|<span data-ttu-id="401ff-143">Almacenamiento</span><span class="sxs-lookup"><span data-stu-id="401ff-143">Storage</span></span>|  
|----------|-------------|  
|<span data-ttu-id="401ff-144">Las credenciales de presentación, como el nombre de usuario, certificados X.509, tokens de Kerberos, y referencias a las credenciales.</span><span class="sxs-lookup"><span data-stu-id="401ff-144">Presentation credentials, such as username, X.509 certificates, Kerberos tokens, and references to credentials.</span></span>|<span data-ttu-id="401ff-145">Mecanismos de administración de credencial de Windows estándar como el almacén de certificados de Windows.</span><span class="sxs-lookup"><span data-stu-id="401ff-145">Standard Windows credential management mechanisms such as the Windows certificate store.</span></span>|  
|<span data-ttu-id="401ff-146">Información de pertenencia del usuario, como nombres de usuario y contraseñas.</span><span class="sxs-lookup"><span data-stu-id="401ff-146">User membership information, such as usernames and passwords.</span></span>|[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] <span data-ttu-id="401ff-147">proveedores de pertenencia.</span><span class="sxs-lookup"><span data-stu-id="401ff-147">membership providers.</span></span>|  
|<span data-ttu-id="401ff-148">Información de identidad sobre el servicio utilizado para autenticar el servicio a los clientes.</span><span class="sxs-lookup"><span data-stu-id="401ff-148">Identity information about the service used to authenticate the service to clients.</span></span>|<span data-ttu-id="401ff-149">La dirección del extremo del servicio.</span><span class="sxs-lookup"><span data-stu-id="401ff-149">Endpoint address of the service.</span></span>|  
|<span data-ttu-id="401ff-150">Información del agente de llamada.</span><span class="sxs-lookup"><span data-stu-id="401ff-150">Caller information.</span></span>|<span data-ttu-id="401ff-151">Registros de auditoría.</span><span class="sxs-lookup"><span data-stu-id="401ff-151">Auditing logs.</span></span>|  
  
## <a name="auditing"></a><span data-ttu-id="401ff-152">Auditoría</span><span class="sxs-lookup"><span data-stu-id="401ff-152">Auditing</span></span>  
 <span data-ttu-id="401ff-153">La auditoría registra si se ha completado o se ha producido un error en la autenticación y eventos de autorización.</span><span class="sxs-lookup"><span data-stu-id="401ff-153">Auditing records the success and failure of authentication and authorization events.</span></span> <span data-ttu-id="401ff-154">Los registros de la auditoría contienen los datos siguientes: servicio URI, acción URI y la identificación del agente de llamada.</span><span class="sxs-lookup"><span data-stu-id="401ff-154">Auditing records contain the following data: service URI, action URI, and the caller's identification.</span></span>  
  
 <span data-ttu-id="401ff-155">La auditoría también registra cuando el administrador modifica la configuración de registro de mensajes (activándolo o desactivándolo), porque el registro de mensajes puede registrar los datos específicos de la aplicación en encabezados y cuerpos.</span><span class="sxs-lookup"><span data-stu-id="401ff-155">Auditing also records when the administrator modifies the configuration of message logging (turning it on or off), because message logging may log application-specific data in headers and bodies.</span></span> <span data-ttu-id="401ff-156">Para [!INCLUDE[wxp](../../../includes/wxp-md.md)], un registro está registrado en el registro de eventos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="401ff-156">For [!INCLUDE[wxp](../../../includes/wxp-md.md)], a record is logged in the application event log.</span></span> <span data-ttu-id="401ff-157">Para [!INCLUDE[wv](../../../includes/wv-md.md)] y [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], un registro está registrado en el registro de eventos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="401ff-157">For [!INCLUDE[wv](../../../includes/wv-md.md)] and [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], a record is logged in the security event log.</span></span>  
  
## <a name="transactions"></a><span data-ttu-id="401ff-158">Transacciones</span><span class="sxs-lookup"><span data-stu-id="401ff-158">Transactions</span></span>  
 <span data-ttu-id="401ff-159">La característica de transacciones proporciona servicios transaccionales a una aplicación de WCF.</span><span class="sxs-lookup"><span data-stu-id="401ff-159">The transactions feature provides transactional services to a WCF application.</span></span>  
  
 <span data-ttu-id="401ff-160">Los encabezados de las transacciones utilizados en la propagación de la transacción pueden contener los id. de transacción o id. de inscripción, que son GUID.</span><span class="sxs-lookup"><span data-stu-id="401ff-160">Transaction headers used in transaction propagation may contain Transaction IDs or Enlistment IDs, which are GUIDs.</span></span>  
  
 <span data-ttu-id="401ff-161">La característica de las transacciones utiliza el Administrador de transacciones (un componente de Windows) de Microsoft DTC (Coordinador de transacciones distribuidas) para administrar el estado de la transacción.</span><span class="sxs-lookup"><span data-stu-id="401ff-161">The Transactions feature uses the Microsoft Distributed Transaction Coordinator (MSDTC) Transaction Manager (a Windows component) to manage transaction state.</span></span> <span data-ttu-id="401ff-162">De forma predeterminada, se cifran las comunicaciones entre Administradores de las Transacciones.</span><span class="sxs-lookup"><span data-stu-id="401ff-162">By default, communications between Transactions Managers are encrypted.</span></span> <span data-ttu-id="401ff-163">Los administradores de transacciones pueden registrar referencias de extremo, id. de transacción e id. de inscripción como parte de su estado duradero.</span><span class="sxs-lookup"><span data-stu-id="401ff-163">Transaction Managers may log endpoint references, Transaction IDs, and Enlistment IDs as part of their durable state.</span></span> <span data-ttu-id="401ff-164">La duración del archivo de registro del Administrador de la Transacción determina la duración de este estado.</span><span class="sxs-lookup"><span data-stu-id="401ff-164">The lifetime of this state is determined by the lifetime of the Transaction Manager’s log file.</span></span> <span data-ttu-id="401ff-165">El servicio de MSDTC posee y mantiene este registro.</span><span class="sxs-lookup"><span data-stu-id="401ff-165">The MSDTC service owns and maintains this log.</span></span>  
  
 <span data-ttu-id="401ff-166">La característica Transacciones implementa los estándares WS-Coordination y WS-Atomic Transaction.</span><span class="sxs-lookup"><span data-stu-id="401ff-166">The Transactions feature implements the WS-Coordination and WS-Atomic Transaction standards.</span></span>  
  
## <a name="reliable-sessions"></a><span data-ttu-id="401ff-167">Sesiones de confianza</span><span class="sxs-lookup"><span data-stu-id="401ff-167">Reliable Sessions</span></span>  
 <span data-ttu-id="401ff-168">Las sesiones confiables en WCF proporcionan a la transferencia de mensajes cuando se producen errores de intermediarios o de transporte.</span><span class="sxs-lookup"><span data-stu-id="401ff-168">Reliable sessions in WCF provide the transfer of messages when transport or intermediary failures occur.</span></span> <span data-ttu-id="401ff-169">Incluso proporcionan una transferencia de mensajes,, exactamente una vez, cuando el transporte subyacente desconecta (por ejemplo, una conexión TCP en una red inalámbrica) o pierde un mensaje (un proxy HTTP al colocar un mensaje de salida o entrante).</span><span class="sxs-lookup"><span data-stu-id="401ff-169">They provide an exactly-once transfer of messages even when the underlying transport disconnects (for example, a TCP connection on a wireless network) or loses a message (an HTTP proxy dropping an outgoing or incoming message).</span></span> <span data-ttu-id="401ff-170">Las sesiones de confianza también recuperan el mensaje reordenando (como puede pasar en el caso de enrutamiento de varias rutas de acceso), conservando el orden en el que se enviaron los mensajes.</span><span class="sxs-lookup"><span data-stu-id="401ff-170">Reliable sessions also recover message reordering (as may happen in the case of multipath routing), preserving the order in which the messages were sent.</span></span>  
  
 <span data-ttu-id="401ff-171">Las sesiones de confianza se implementan utilizando el protocolo WS-ReliableMessaging (WS-RM).</span><span class="sxs-lookup"><span data-stu-id="401ff-171">Reliable sessions are implemented using the WS-ReliableMessaging (WS-RM) protocol.</span></span> <span data-ttu-id="401ff-172">Agregan los encabezados WS-RM que contienen información de la sesión, la cual se utiliza para identificar todos los mensajes asociados a una sesión de confianza determinada.</span><span class="sxs-lookup"><span data-stu-id="401ff-172">They add WS-RM headers that contain session information, which is used to identify all messages associated with a particular reliable session.</span></span> <span data-ttu-id="401ff-173">Cada sesión de WS-RM tiene un identificador, que es un GUID.</span><span class="sxs-lookup"><span data-stu-id="401ff-173">Each WS-RM session has an identifier, which is a GUID.</span></span>  
  
 <span data-ttu-id="401ff-174">No se retiene información personal en el equipo de usuario final.</span><span class="sxs-lookup"><span data-stu-id="401ff-174">No personal information is retained on the end-user's machine.</span></span>  
  
## <a name="queued-channels"></a><span data-ttu-id="401ff-175">Canals en la cola</span><span class="sxs-lookup"><span data-stu-id="401ff-175">Queued Channels</span></span>  
 <span data-ttu-id="401ff-176">Las colas almacenan mensajes de una aplicación emisora en nombre de una aplicación receptora y, a continuación, reenvían estos mensajes a la aplicación receptora.</span><span class="sxs-lookup"><span data-stu-id="401ff-176">Queues store messages from a sending application on behalf of a receiving application and later forward these messages to the receiving application.</span></span> <span data-ttu-id="401ff-177">Ayudan a garantizar la transferencia de mensajes desde aplicaciones de envío a aplicaciones de recepción cuando, por ejemplo, la aplicación receptora es transitoria.</span><span class="sxs-lookup"><span data-stu-id="401ff-177">They help ensure the transfer of messages from sending applications to receiving applications when, for example, the receiving application is transient.</span></span> <span data-ttu-id="401ff-178">WCF proporciona compatibilidad para poner en cola utilizando Microsoft Message Queuing (MSMQ) como transporte.</span><span class="sxs-lookup"><span data-stu-id="401ff-178">WCF provides support for queuing by using Microsoft Message Queuing (MSMQ) as a transport.</span></span>  
  
 <span data-ttu-id="401ff-179">La característica de los canales en cola no agrega encabezados a un mensaje.</span><span class="sxs-lookup"><span data-stu-id="401ff-179">The queued channels feature does not add headers to a message.</span></span> <span data-ttu-id="401ff-180">En su lugar, crea un mensaje de Message Queuing con propiedades de mensaje de Message Queuing adecuadas establecidas e invoca los métodos Message Queuing para colocar el mensaje en la cola de Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="401ff-180">Instead it creates a Message Queuing message with appropriate Message Queuing message properties set, and invokes Message Queuing methods to put the message in the Message Queuing queue.</span></span> <span data-ttu-id="401ff-181">Message Queuing es un componente opcional distribuido con Windows.</span><span class="sxs-lookup"><span data-stu-id="401ff-181">Message Queuing is an optional component that ships with Windows.</span></span>  
  
 <span data-ttu-id="401ff-182">No se retiene información en el equipo del usuario final mediante la característica de canal en cola, porque utiliza la infraestructura Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="401ff-182">No information is retained on the end-user's machine by the queued channels feature, because it uses Message Queuing as the queuing infrastructure.</span></span>  
  
## <a name="com-integration"></a><span data-ttu-id="401ff-183">Integración de COM+</span><span class="sxs-lookup"><span data-stu-id="401ff-183">COM+ Integration</span></span>  
 <span data-ttu-id="401ff-184">Esta característica ajusta la funcionalidad de COM y COM + existente para crear servicios que son compatibles con los servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="401ff-184">This feature wraps existing COM and COM+ functionality to create services that are compatible with WCF services.</span></span> <span data-ttu-id="401ff-185">Esta característica no utiliza los encabezados específicos y no retiene los datos en el equipo del usuario final.</span><span class="sxs-lookup"><span data-stu-id="401ff-185">This feature does not use specific headers and it does not retain data on the end-user's machine.</span></span>  
  
## <a name="com-service-moniker"></a><span data-ttu-id="401ff-186">Moniker de servicio COM</span><span class="sxs-lookup"><span data-stu-id="401ff-186">COM Service Moniker</span></span>  
 <span data-ttu-id="401ff-187">Esto proporciona un contenedor no administrado a un cliente WCF estándar.</span><span class="sxs-lookup"><span data-stu-id="401ff-187">This provides an unmanaged wrapper to a standard WCF client.</span></span> <span data-ttu-id="401ff-188">Esta característica no tiene encabezados específicos en la conexión ni conserva datos en el equipo.</span><span class="sxs-lookup"><span data-stu-id="401ff-188">This feature does not have specific headers on the wire nor does it persist data on the machine.</span></span>  
  
## <a name="peer-channel"></a><span data-ttu-id="401ff-189">Canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="401ff-189">Peer Channel</span></span>  
 <span data-ttu-id="401ff-190">Un canal del mismo nivel habilita el desarrollo de aplicaciones multipartidarias utilizando WCF.</span><span class="sxs-lookup"><span data-stu-id="401ff-190">A peer channel enables development of multiparty applications using WCF.</span></span> <span data-ttu-id="401ff-191">La mensajería multipartidaria se produce en el contexto de una malla.</span><span class="sxs-lookup"><span data-stu-id="401ff-191">Multiparty messaging occurs in the context of a mesh.</span></span> <span data-ttu-id="401ff-192">Un nombre al cual se pueden unir los nodos identifica las mallas.</span><span class="sxs-lookup"><span data-stu-id="401ff-192">Meshes are identified by a name that nodes can join.</span></span> <span data-ttu-id="401ff-193">Cada nodo del canal del mismo nivel crea un agente de escucha de TCP en un puerto especificado por el usuario y establece las conexiones con otros nodos en la malla para garantizar la resiliencia.</span><span class="sxs-lookup"><span data-stu-id="401ff-193">Each node in the peer channel creates a TCP listener at a user-specified port and establishes connections with other nodes in the mesh to ensure resiliency.</span></span> <span data-ttu-id="401ff-194">Para conectar a otros nodos en la malla, los nodos también intercambian algunos datos, incluso la dirección del agente de escucha y las direcciones IP del equipo, con otros nodos de la malla.</span><span class="sxs-lookup"><span data-stu-id="401ff-194">To connect to other nodes in the mesh, nodes also exchange some data, including the listener address and the machine's IP addresses, with other nodes in the mesh.</span></span> <span data-ttu-id="401ff-195">Los mensajes enviados en la malla pueden contener información de seguridad que pertenece al remitente para evitar que se suplante y se manipule el mensaje.</span><span class="sxs-lookup"><span data-stu-id="401ff-195">Messages sent around in the mesh can contain security information that pertains to the sender to prevent message spoofing and tampering.</span></span>  
  
 <span data-ttu-id="401ff-196">No se almacena información personal en el equipo de usuario final.</span><span class="sxs-lookup"><span data-stu-id="401ff-196">No personal information is stored on the end-user's machine.</span></span>  
  
## <a name="it-professional-experience"></a><span data-ttu-id="401ff-197">Experiencia profesional de TI</span><span class="sxs-lookup"><span data-stu-id="401ff-197">IT Professional Experience</span></span>  
  
### <a name="tracing"></a><span data-ttu-id="401ff-198">Traza</span><span class="sxs-lookup"><span data-stu-id="401ff-198">Tracing</span></span>  
 <span data-ttu-id="401ff-199">La característica de diagnóstico de la infraestructura de WCF registra los mensajes que pasan a través del transporte y las capas del modelo de servicio y las actividades y eventos asociados con estos mensajes.</span><span class="sxs-lookup"><span data-stu-id="401ff-199">The diagnostics feature of the WCF infrastructure logs messages that pass through the transport and service model layers, and the activities and events associated with these messages.</span></span> <span data-ttu-id="401ff-200">Esta característica está desactivada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="401ff-200">This feature is turned off by default.</span></span> <span data-ttu-id="401ff-201">Se habilita mediante el archivo de configuración de la aplicación y se puede modificar el comportamiento de seguimiento mediante el proveedor WMI de WCF en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="401ff-201">It is enabled using the application’s configuration file and the tracing behavior may be modified using the WCF WMI provider at run time.</span></span> <span data-ttu-id="401ff-202">Cuando se habilita, la infraestructura de la traza emite una traza de diagnóstico que contiene mensajes, actividades y eventos de procesamiento a los agentes de escucha configurados.</span><span class="sxs-lookup"><span data-stu-id="401ff-202">When enabled, the tracing infrastructure emits a diagnostic trace that contains messages, activities, and processing events to configured listeners.</span></span> <span data-ttu-id="401ff-203">Las opciones de configuración del agente de escucha del administrador determinan el formato y ubicación del resultado, pero es normalmente un archivo con formato XML.</span><span class="sxs-lookup"><span data-stu-id="401ff-203">The format and location of the output are determined by the administrator’s listener configuration choices, but is typically an XML formatted file.</span></span> <span data-ttu-id="401ff-204">El administrador es responsable de establecer la lista de control de acceso (ACL) en los archivos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="401ff-204">The administrator is responsible for setting the access control list (ACL) on the trace files.</span></span> <span data-ttu-id="401ff-205">En particular, cuando está hospedado por el Sistema de Activación de Windows (WAS), el administrador debería asegurarse de que los archivos no provienen del directorio raíz virtual público si no se desea.</span><span class="sxs-lookup"><span data-stu-id="401ff-205">In particular, when hosted by Windows Activation System (WAS), the administrator should make sure the files are not served from the public virtual root directory if that is not desired.</span></span>  
  
 <span data-ttu-id="401ff-206">Hay dos tipos de seguimiento: Registro de mensajes y el diagnóstico de modelo de servicio de seguimiento, se describen en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="401ff-206">There are two types of tracing: Message logging and Service Model diagnostic tracing, described in the following section.</span></span> <span data-ttu-id="401ff-207">Cada tipo se configura a través de su propio origen de traza: <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> y <xref:System.ServiceModel>.</span><span class="sxs-lookup"><span data-stu-id="401ff-207">Each type is configured through its own trace source: <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> and <xref:System.ServiceModel>.</span></span> <span data-ttu-id="401ff-208">Estos orígenes de traza de registro capturan locales a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="401ff-208">Both of these logging trace sources capture data that is local to the application.</span></span>  
  
### <a name="message-logging"></a><span data-ttu-id="401ff-209">Registro de mensajes</span><span class="sxs-lookup"><span data-stu-id="401ff-209">Message Logging</span></span>  
 <span data-ttu-id="401ff-210">El origen de traza del registro de mensajes (<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>) permite a un administrador registrar los mensajes que fluyen a través del sistema.</span><span class="sxs-lookup"><span data-stu-id="401ff-210">The message logging trace source (<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>) allows an administrator to log the messages that flow through the system.</span></span> <span data-ttu-id="401ff-211">A través de la configuración, el usuario puede decidir si quiere registrar mensajes completos o solamente encabezados de mensaje, registrar en el transporte y/o niveles de modelo de servicio y si quiere incluir mensajes incorrectos.</span><span class="sxs-lookup"><span data-stu-id="401ff-211">Through configuration, the user may decide to log entire messages or message headers only, whether to log at the transport and/or service model layers, and whether to include malformed messages.</span></span> <span data-ttu-id="401ff-212">Además, el usuario puede configurar el filtro para restringir qué mensajes están registrados.</span><span class="sxs-lookup"><span data-stu-id="401ff-212">Also, the user may configure filtering to restrict which messages are logged.</span></span>  
  
 <span data-ttu-id="401ff-213">De forma predeterminada, el registro de mensajes está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="401ff-213">By default, message logging is disabled.</span></span> <span data-ttu-id="401ff-214">El administrador del equipo local puede evitar que el administrador del nivel de la aplicación active el registro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="401ff-214">The local machine administrator can prevent the application-level administrator from turning message logging on.</span></span>  
  
#### <a name="encrypted-and-decrypted-message-logging"></a><span data-ttu-id="401ff-215">Registro de mensajes cifrado y descifrado</span><span class="sxs-lookup"><span data-stu-id="401ff-215">Encrypted and Decrypted Message Logging</span></span>  
 <span data-ttu-id="401ff-216">Los mensajes se registran, cifran o descifran, tal y como se ha descrito en los términos siguientes.</span><span class="sxs-lookup"><span data-stu-id="401ff-216">Messages are logged, encrypted, or decrypted, as described in the following terms.</span></span>  
  
 <span data-ttu-id="401ff-217">Registro de transporte</span><span class="sxs-lookup"><span data-stu-id="401ff-217">Transport Logging</span></span>  
 <span data-ttu-id="401ff-218">Registra los mensajes recibidos y enviados en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="401ff-218">Logs messages received and sent at the transport level.</span></span> <span data-ttu-id="401ff-219">Estos mensajes contienen todos los encabezados y se pueden cifrar antes de ser enviados en la conexión y al recibirse.</span><span class="sxs-lookup"><span data-stu-id="401ff-219">These messages contain all headers, and may be encrypted before being sent on the wire and when being received.</span></span>  
  
 <span data-ttu-id="401ff-220">Si se cifran los mensajes antes de ser enviados en la conexión y cuando se reciben, están registrados y cifrados también.</span><span class="sxs-lookup"><span data-stu-id="401ff-220">If messages are encrypted before being sent on the wire and when they are received, they are logged encrypted as well.</span></span> <span data-ttu-id="401ff-221">Una excepción es cuando se utiliza un protocolo de seguridad (https): están registrados y descifrado antes de ser enviados y después de ser recibidos, incluso si se cifran en la conexión.</span><span class="sxs-lookup"><span data-stu-id="401ff-221">An exception is when a security protocol is used (https): they are then logged decrypted before being sent and after being received even if they are encrypted on the wire.</span></span>  
  
 <span data-ttu-id="401ff-222">Registro del servicio</span><span class="sxs-lookup"><span data-stu-id="401ff-222">Service Logging</span></span>  
 <span data-ttu-id="401ff-223">Registra mensajes recibidos o enviados en el nivel de modelo del servicio, después de que se haya producido el procesamiento del encabezado del canal procesar, justo antes y después de escribir el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="401ff-223">Logs messages received or sent at the service model level, after channel header processing has occurred, just before and after entering user code.</span></span>  
  
 <span data-ttu-id="401ff-224">Se descifran los mensajes registrados en este nivel incluso si se protegieron y cifraron en la conexión.</span><span class="sxs-lookup"><span data-stu-id="401ff-224">Messages logged at this level are decrypted even if they were secured and encrypted on the wire.</span></span>  
  
 <span data-ttu-id="401ff-225">Registro de mensajes incorrectos</span><span class="sxs-lookup"><span data-stu-id="401ff-225">Malformed Message Logging</span></span>  
 <span data-ttu-id="401ff-226">Registra mensajes que no se puede entender o procesar la infraestructura de WCF.</span><span class="sxs-lookup"><span data-stu-id="401ff-226">Logs messages that the WCF infrastructure cannot understand or process.</span></span>  
  
 <span data-ttu-id="401ff-227">Los mensajes están registrados tal cual, es decir, cifrados o no</span><span class="sxs-lookup"><span data-stu-id="401ff-227">Messages are logged as-is, that is, encrypted or not</span></span>  
  
 <span data-ttu-id="401ff-228">Cuando los mensajes se registran formato sin cifrar o descifrar, de forma predeterminada, WCF quita las claves de seguridad y potencialmente datos personales de los mensajes antes de registrarlos.</span><span class="sxs-lookup"><span data-stu-id="401ff-228">When messages are logged in decrypted or unencrypted form, by default WCF removes security keys and potentially personal information from the messages before logging them.</span></span> <span data-ttu-id="401ff-229">Las secciones siguientes describen qué información se quita, y cuándo.</span><span class="sxs-lookup"><span data-stu-id="401ff-229">The next sections describe what information is removed, and when.</span></span> <span data-ttu-id="401ff-230">El administrador del equipo e implementador de la aplicación deben tomar ciertas medidas de configuración para cambiar el comportamiento predeterminado con el fin de registrar las claves y potencialmente datos personales.</span><span class="sxs-lookup"><span data-stu-id="401ff-230">The machine administrator and application deployer must both take certain configuration actions to change the default behavior to log keys and potentially personal information.</span></span>  
  
#### <a name="information-removed-from-message-headers-when-logging-decryptedunencrypted-messages"></a><span data-ttu-id="401ff-231">Información quitada de los encabezados del mensaje al registrar mensajes descifrados/no cifrados</span><span class="sxs-lookup"><span data-stu-id="401ff-231">Information Removed from Message Headers When Logging Decrypted/Unencrypted Messages</span></span>  
 <span data-ttu-id="401ff-232">Cuando los mensajes están registrados en forma de descifrados/no cifrados, las claves de seguridad y potencialmente los datos personales se quitan de forma predeterminada de los encabezados del mensaje y los cuerpos del mensaje antes de registrarse.</span><span class="sxs-lookup"><span data-stu-id="401ff-232">When messages are logged in decrypted/unencrypted form, security keys and potentially personal information are removed by default from message headers and message bodies before they are logged.</span></span> <span data-ttu-id="401ff-233">En la lista siguiente se muestra lo que WCF considera las claves y potencialmente datos personales.</span><span class="sxs-lookup"><span data-stu-id="401ff-233">The following list shows what WCF considers keys and potentially personal information.</span></span>  
  
 <span data-ttu-id="401ff-234">Claves que se quitan:</span><span class="sxs-lookup"><span data-stu-id="401ff-234">Keys that are removed:</span></span>  
  
 <span data-ttu-id="401ff-235">\- Para obtener más xmlns:wst = "http://schemas.xmlsoap.org/ws/2004/04/trust" y xmlns:wst = "http://schemas.xmlsoap.org/ws/2005/02/trust"</span><span class="sxs-lookup"><span data-stu-id="401ff-235">\- For xmlns:wst="http://schemas.xmlsoap.org/ws/2004/04/trust" and xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"</span></span>  
  
 <span data-ttu-id="401ff-236">wst:BinarySecret</span><span class="sxs-lookup"><span data-stu-id="401ff-236">wst:BinarySecret</span></span>  
  
 <span data-ttu-id="401ff-237">wst:Entropy</span><span class="sxs-lookup"><span data-stu-id="401ff-237">wst:Entropy</span></span>  
  
 <span data-ttu-id="401ff-238">\- Para obtener más xmlns:wsse = "http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" y xmlns:wsse = "http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span><span class="sxs-lookup"><span data-stu-id="401ff-238">\- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span></span>  
  
 <span data-ttu-id="401ff-239">wsse:Password</span><span class="sxs-lookup"><span data-stu-id="401ff-239">wsse:Password</span></span>  
  
 <span data-ttu-id="401ff-240">wsse:Nonce</span><span class="sxs-lookup"><span data-stu-id="401ff-240">wsse:Nonce</span></span>  
  
 <span data-ttu-id="401ff-241">Datos personales posibles que se quitan:</span><span class="sxs-lookup"><span data-stu-id="401ff-241">Potentially personal information that is removed:</span></span>  
  
 <span data-ttu-id="401ff-242">\- Para obtener más xmlns:wsse = "http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" y xmlns:wsse = "http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span><span class="sxs-lookup"><span data-stu-id="401ff-242">\- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span></span>  
  
 <span data-ttu-id="401ff-243">wsse:Username</span><span class="sxs-lookup"><span data-stu-id="401ff-243">wsse:Username</span></span>  
  
 <span data-ttu-id="401ff-244">wsse:BinarySecurityToken</span><span class="sxs-lookup"><span data-stu-id="401ff-244">wsse:BinarySecurityToken</span></span>  
  
 <span data-ttu-id="401ff-245">\- Para xmlns: SAML = "urn: oasis: nombres: tc: SAML:1.0:assertion" se quitan los elementos en negrita (abajo):</span><span class="sxs-lookup"><span data-stu-id="401ff-245">\- For xmlns:saml="urn:oasis:names:tc:SAML:1.0:assertion" the items in bold (below) are removed:</span></span>  
  
 <span data-ttu-id="401ff-246">\<Aserción</span><span class="sxs-lookup"><span data-stu-id="401ff-246">\<Assertion</span></span>  
  
 <span data-ttu-id="401ff-247">MajorVersion="1"</span><span class="sxs-lookup"><span data-stu-id="401ff-247">MajorVersion="1"</span></span>  
  
 <span data-ttu-id="401ff-248">MinorVersion="1"</span><span class="sxs-lookup"><span data-stu-id="401ff-248">MinorVersion="1"</span></span>  
  
 <span data-ttu-id="401ff-249">AssertionId =" [ID]"</span><span class="sxs-lookup"><span data-stu-id="401ff-249">AssertionId="[ID]"</span></span>  
  
 <span data-ttu-id="401ff-250">Issuer="[string]"</span><span class="sxs-lookup"><span data-stu-id="401ff-250">Issuer="[string]"</span></span>  
  
 <span data-ttu-id="401ff-251">IssueInstant="[dateTime]"</span><span class="sxs-lookup"><span data-stu-id="401ff-251">IssueInstant="[dateTime]"</span></span>  
  
 >  
  
 <span data-ttu-id="401ff-252">\<Condiciones NotBefore = "[dateTime]" NotOnOrAfter = "[fecha y hora]" ></span><span class="sxs-lookup"><span data-stu-id="401ff-252">\<Conditions NotBefore="[dateTime]" NotOnOrAfter="[dateTime]"></span></span>  
  
 <span data-ttu-id="401ff-253">\<AudienceRestrictionCondition></span><span class="sxs-lookup"><span data-stu-id="401ff-253">\<AudienceRestrictionCondition></span></span>  
  
 <span data-ttu-id="401ff-254">\<Audiencia > [uri]\</Audience > +</span><span class="sxs-lookup"><span data-stu-id="401ff-254">\<Audience>[uri]\</Audience>+</span></span>  
  
 <span data-ttu-id="401ff-255">\</AudienceRestrictionCondition>\*</span><span class="sxs-lookup"><span data-stu-id="401ff-255">\</AudienceRestrictionCondition>\*</span></span>  
  
 <span data-ttu-id="401ff-256">\<DoNotCacheCondition />\*</span><span class="sxs-lookup"><span data-stu-id="401ff-256">\<DoNotCacheCondition />\*</span></span>  
  
 <span data-ttu-id="401ff-257"><\!--tipo base abstracto</span><span class="sxs-lookup"><span data-stu-id="401ff-257"><\!-- abstract base type</span></span>  
  
 <span data-ttu-id="401ff-258">\<Condición / > \*</span><span class="sxs-lookup"><span data-stu-id="401ff-258">\<Condition />\*</span></span>  
  
 -->  
  
 <span data-ttu-id="401ff-259">\<¿/ Condiciones >?</span><span class="sxs-lookup"><span data-stu-id="401ff-259">\</Conditions>?</span></span>  
  
 <span data-ttu-id="401ff-260">\<Consejos ></span><span class="sxs-lookup"><span data-stu-id="401ff-260">\<Advice></span></span>  
  
 <span data-ttu-id="401ff-261">\<AssertionIDReference>[ID]\</AssertionIDReference>\*</span><span class="sxs-lookup"><span data-stu-id="401ff-261">\<AssertionIDReference>[ID]\</AssertionIDReference>\*</span></span>  
  
 <span data-ttu-id="401ff-262">\<Aserción > [aserción]\</Assertion > \*</span><span class="sxs-lookup"><span data-stu-id="401ff-262">\<Assertion>[assertion]\</Assertion>\*</span></span>  
  
 <span data-ttu-id="401ff-263">[any]\*</span><span class="sxs-lookup"><span data-stu-id="401ff-263">[any]\*</span></span>  
  
 <span data-ttu-id="401ff-264">\<¿O aviso >?</span><span class="sxs-lookup"><span data-stu-id="401ff-264">\</Advice>?</span></span>  
  
 <span data-ttu-id="401ff-265"><\!--Tipos base abstractos</span><span class="sxs-lookup"><span data-stu-id="401ff-265"><\!-- Abstract base types</span></span>  
  
 <span data-ttu-id="401ff-266">\<Instrucción / > \*</span><span class="sxs-lookup"><span data-stu-id="401ff-266">\<Statement />\*</span></span>  
  
 <span data-ttu-id="401ff-267">\<SubjectStatement></span><span class="sxs-lookup"><span data-stu-id="401ff-267">\<SubjectStatement></span></span>  
  
 <span data-ttu-id="401ff-268">\<Subject></span><span class="sxs-lookup"><span data-stu-id="401ff-268">\<Subject></span></span>  
  
 `<NameIdentifier`  
  
 `NameQualifier="[string]"?`  
  
 `Format="[uri]"?`  
  
 `>`  
  
 `[string]`  
  
 `</NameIdentifier>?`  
  
 <span data-ttu-id="401ff-269">\<SubjectConfirmation></span><span class="sxs-lookup"><span data-stu-id="401ff-269">\<SubjectConfirmation></span></span>  
  
 <span data-ttu-id="401ff-270">\<ConfirmationMethod > [anyUri]\</ConfirmationMethod > +</span><span class="sxs-lookup"><span data-stu-id="401ff-270">\<ConfirmationMethod>[anyUri]\</ConfirmationMethod>+</span></span>  
  
 <span data-ttu-id="401ff-271">\<SubjectConfirmationData>[any]\</SubjectConfirmationData>?</span><span class="sxs-lookup"><span data-stu-id="401ff-271">\<SubjectConfirmationData>[any]\</SubjectConfirmationData>?</span></span>  
  
 <span data-ttu-id="401ff-272">\<ds:KeyInfo>...\</ds:KeyInfo>?</span><span class="sxs-lookup"><span data-stu-id="401ff-272">\<ds:KeyInfo>...\</ds:KeyInfo>?</span></span>  
  
 <span data-ttu-id="401ff-273">\</SubjectConfirmation>?</span><span class="sxs-lookup"><span data-stu-id="401ff-273">\</SubjectConfirmation>?</span></span>  
  
 <span data-ttu-id="401ff-274">\</Subject></span><span class="sxs-lookup"><span data-stu-id="401ff-274">\</Subject></span></span>  
  
 <span data-ttu-id="401ff-275">\</SubjectStatement>\*</span><span class="sxs-lookup"><span data-stu-id="401ff-275">\</SubjectStatement>\*</span></span>  
  
 -->  
  
 <span data-ttu-id="401ff-276">\<AuthenticationStatement</span><span class="sxs-lookup"><span data-stu-id="401ff-276">\<AuthenticationStatement</span></span>  
  
 <span data-ttu-id="401ff-277">AuthenticationMethod =" [uri]"</span><span class="sxs-lookup"><span data-stu-id="401ff-277">AuthenticationMethod="[uri]"</span></span>  
  
 <span data-ttu-id="401ff-278">AuthenticationInstant="[dateTime]"</span><span class="sxs-lookup"><span data-stu-id="401ff-278">AuthenticationInstant="[dateTime]"</span></span>  
  
 >  
  
 <span data-ttu-id="401ff-279">[Subject]</span><span class="sxs-lookup"><span data-stu-id="401ff-279">[Subject]</span></span>  
  
 `<SubjectLocality`  
  
 `IPAddress="[string]"?`  
  
 `DNSAddress="[string]"?`  
  
 `/>?`  
  
 <span data-ttu-id="401ff-280"><AuthorityBinding</span><span class="sxs-lookup"><span data-stu-id="401ff-280"><AuthorityBinding</span></span>  
  
 <span data-ttu-id="401ff-281">AuthorityKind =" [QName]"</span><span class="sxs-lookup"><span data-stu-id="401ff-281">AuthorityKind="[QName]"</span></span>  
  
 <span data-ttu-id="401ff-282">Location="[uri]"</span><span class="sxs-lookup"><span data-stu-id="401ff-282">Location="[uri]"</span></span>  
  
 <span data-ttu-id="401ff-283">Enlace =" [uri]"</span><span class="sxs-lookup"><span data-stu-id="401ff-283">Binding="[uri]"</span></span>  
  
 />*  
  
 <span data-ttu-id="401ff-284">\</AuthenticationStatement>\*</span><span class="sxs-lookup"><span data-stu-id="401ff-284">\</AuthenticationStatement>\*</span></span>  
  
 <span data-ttu-id="401ff-285">\<AttributeStatement></span><span class="sxs-lookup"><span data-stu-id="401ff-285">\<AttributeStatement></span></span>  
  
 <span data-ttu-id="401ff-286">[Subject]</span><span class="sxs-lookup"><span data-stu-id="401ff-286">[Subject]</span></span>  
  
 <span data-ttu-id="401ff-287">\<Atributo</span><span class="sxs-lookup"><span data-stu-id="401ff-287">\<Attribute</span></span>  
  
 <span data-ttu-id="401ff-288">AttributeName="[string]"</span><span class="sxs-lookup"><span data-stu-id="401ff-288">AttributeName="[string]"</span></span>  
  
 <span data-ttu-id="401ff-289">AttributeNamespace =" [uri]"</span><span class="sxs-lookup"><span data-stu-id="401ff-289">AttributeNamespace="[uri]"</span></span>  
  
 >  
  
 `<AttributeValue>[any]</AttributeValue>+`  
  
 <span data-ttu-id="401ff-290">\</Attribute>+</span><span class="sxs-lookup"><span data-stu-id="401ff-290">\</Attribute>+</span></span>  
  
 <span data-ttu-id="401ff-291">\</AttributeStatement>\*</span><span class="sxs-lookup"><span data-stu-id="401ff-291">\</AttributeStatement>\*</span></span>  
  
 <span data-ttu-id="401ff-292">\<AuthorizationDecisionStatement</span><span class="sxs-lookup"><span data-stu-id="401ff-292">\<AuthorizationDecisionStatement</span></span>  
  
 <span data-ttu-id="401ff-293">Resource =" [uri]"</span><span class="sxs-lookup"><span data-stu-id="401ff-293">Resource="[uri]"</span></span>  
  
 <span data-ttu-id="401ff-294">Decisión = "[permitir&#124;denegar&#124;indeterminado]"</span><span class="sxs-lookup"><span data-stu-id="401ff-294">Decision="[Permit&#124;Deny&#124;Indeterminate]"</span></span>  
  
 >  
  
 <span data-ttu-id="401ff-295">[Subject]</span><span class="sxs-lookup"><span data-stu-id="401ff-295">[Subject]</span></span>  
  
 <span data-ttu-id="401ff-296">\<Action Namespace="[uri]">[string]\</Action>+</span><span class="sxs-lookup"><span data-stu-id="401ff-296">\<Action Namespace="[uri]">[string]\</Action>+</span></span>  
  
 <span data-ttu-id="401ff-297">\<Evidence></span><span class="sxs-lookup"><span data-stu-id="401ff-297">\<Evidence></span></span>  
  
 <span data-ttu-id="401ff-298">\<AssertionIDReference>[ID]\</AssertionIDReference>+</span><span class="sxs-lookup"><span data-stu-id="401ff-298">\<AssertionIDReference>[ID]\</AssertionIDReference>+</span></span>  
  
 <span data-ttu-id="401ff-299">\<Aserción > [aserción]\</Assertion > +</span><span class="sxs-lookup"><span data-stu-id="401ff-299">\<Assertion>[assertion]\</Assertion>+</span></span>  
  
 <span data-ttu-id="401ff-300">\</Evidence>?</span><span class="sxs-lookup"><span data-stu-id="401ff-300">\</Evidence>?</span></span>  
  
 <span data-ttu-id="401ff-301">\</AuthorizationDecisionStatement>\*</span><span class="sxs-lookup"><span data-stu-id="401ff-301">\</AuthorizationDecisionStatement>\*</span></span>  
  
 <span data-ttu-id="401ff-302">\</Assertion></span><span class="sxs-lookup"><span data-stu-id="401ff-302">\</Assertion></span></span>  
  
#### <a name="information-removed-from-message-bodies-when-logging-decryptedunencrypted-messages"></a><span data-ttu-id="401ff-303">Información quitada de los cuerpos del mensaje al registrar mensajes descifrados/no cifrados</span><span class="sxs-lookup"><span data-stu-id="401ff-303">Information Removed from Message Bodies When Logging Decrypted/Unencrypted Messages</span></span>  
 <span data-ttu-id="401ff-304">Como se describió anteriormente, WCF quita claves y personales potencialmente conocidos de los encabezados del mensaje para los mensajes registrados descifrados/no cifrados.</span><span class="sxs-lookup"><span data-stu-id="401ff-304">As previously described, WCF removes keys and known potentially personal information from message headers for logged decrypted/unencrypted messages.</span></span> <span data-ttu-id="401ff-305">Además, WCF quita las claves y personales potencialmente conocidos de los cuerpos de mensaje para los elementos del cuerpo y acciones en la lista siguiente, donde se describen los mensajes de seguridad implicados en el intercambio de claves.</span><span class="sxs-lookup"><span data-stu-id="401ff-305">In addition, WCF removes keys and known potentially personal information from message bodies for the body elements and actions in the following list, which describe security messages involved in key exchange.</span></span>  
  
 <span data-ttu-id="401ff-306">Para los siguientes espacios de nombres:</span><span class="sxs-lookup"><span data-stu-id="401ff-306">For the following namespaces:</span></span>  
  
 <span data-ttu-id="401ff-307">xmlns:WST = "http://schemas.xmlsoap.org/ws/2004/04/trust" y xmlns:wst = "http://schemas.xmlsoap.org/ws/2005/02/trust" (por ejemplo, si no hay acciones disponibles)</span><span class="sxs-lookup"><span data-stu-id="401ff-307">xmlns:wst="http://schemas.xmlsoap.org/ws/2004/04/trust" and xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust" (for example, if no action available)</span></span>  
  
 <span data-ttu-id="401ff-308">La información se quita de estos elementos del cuerpo, lo cual implica intercambio de claves:</span><span class="sxs-lookup"><span data-stu-id="401ff-308">Information is removed for these body elements, which involve key exchange:</span></span>  
  
 <span data-ttu-id="401ff-309">wst:RequestSecurityToken</span><span class="sxs-lookup"><span data-stu-id="401ff-309">wst:RequestSecurityToken</span></span>  
  
 <span data-ttu-id="401ff-310">wst:RequestSecurityTokenResponse</span><span class="sxs-lookup"><span data-stu-id="401ff-310">wst:RequestSecurityTokenResponse</span></span>  
  
 <span data-ttu-id="401ff-311">wst:RequestSecurityTokenResponseCollection</span><span class="sxs-lookup"><span data-stu-id="401ff-311">wst:RequestSecurityTokenResponseCollection</span></span>  
  
 <span data-ttu-id="401ff-312">La información también se quita en cada una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="401ff-312">Information is also removed for each of the following Actions:</span></span>  
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Validate`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Validate`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Amend`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Amend`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT-Amend`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT-Amend`
  
#### <a name="no-information-is-removed-from-application-specific-headers-and-body-data"></a><span data-ttu-id="401ff-313">No se quita información de los encabezados y datos del cuerpo específicos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="401ff-313">No Information Is Removed from Application-specific Headers and Body Data</span></span>  
 <span data-ttu-id="401ff-314">WCF no realiza un seguimiento de información personal en encabezados específicos de la aplicación (por ejemplo, las cadenas de consulta) o datos del cuerpo (por ejemplo, el número de tarjeta de crédito).</span><span class="sxs-lookup"><span data-stu-id="401ff-314">WCF does not track personal information in application-specific headers (for example, query strings) or body data (for example, credit card number).</span></span>  
  
 <span data-ttu-id="401ff-315">Cuando el registro de mensajes está activado, los datos personales en encabezados específicos de la aplicación e información del cuerpo pueden estar visibles en los registros.</span><span class="sxs-lookup"><span data-stu-id="401ff-315">When message logging is on, personal information in application-specific headers and body information may be visible in the logs.</span></span> <span data-ttu-id="401ff-316">De nuevo, el implementador de la aplicación es el responsable de establecer las ACL en los archivos de registro y configuración.</span><span class="sxs-lookup"><span data-stu-id="401ff-316">Again, the application deployer is responsible for setting the ACLs on the configuration and log files.</span></span> <span data-ttu-id="401ff-317">También puede desactivar el registro si no desea que esta información esté visible, o puede filtrar fuera esta información de los archivos de registro una vez registrado.</span><span class="sxs-lookup"><span data-stu-id="401ff-317">He also can turn off logging if he does not want this information to be visible, or he may filter out this information from the log files after it is logged.</span></span>  
  
### <a name="service-model-tracing"></a><span data-ttu-id="401ff-318">Traza de modelo de servicio</span><span class="sxs-lookup"><span data-stu-id="401ff-318">Service Model Tracing</span></span>  
 <span data-ttu-id="401ff-319">El origen de la traza de modelo de servicio (<xref:System.ServiceModel>) habilita la traza de las actividades y el segumiento de eventos relacionados con el procesamiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="401ff-319">The Service Model trace source (<xref:System.ServiceModel>) enables tracing of activities and events related to message processing.</span></span> <span data-ttu-id="401ff-320">Esta característica utiliza la funcionalidad de diagnóstico del marco .NET de <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="401ff-320">This feature uses the .NET Framework diagnostic functionality from <xref:System.Diagnostics>.</span></span> <span data-ttu-id="401ff-321">Como con la propiedad <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>, el usuario puede configurar la ubicación y su ACL mediante los archivos de configuración de la aplicación del marco .NET.</span><span class="sxs-lookup"><span data-stu-id="401ff-321">As with the <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> property, the location and its ACL are user-configurable using .NET Framework application configuration files.</span></span> <span data-ttu-id="401ff-322">Como con el registro de mensajes, la ubicación del archivo se configura siempre cuando el administrador habilita la traza; de este modo, el administrador controla el ACL.</span><span class="sxs-lookup"><span data-stu-id="401ff-322">As with message logging, the file location is always configured when the administrator enables tracing; thus, the administrator controls the ACL.</span></span>  
  
 <span data-ttu-id="401ff-323">Las trazas contienen los encabezados del mensaje cuando un mensaje está en ámbito.</span><span class="sxs-lookup"><span data-stu-id="401ff-323">Traces contain message headers when a message is in scope.</span></span> <span data-ttu-id="401ff-324">Se aplican las mismas reglas para ocultar los posibles datos personales en encabezados del mensaje de la sección anterior: los datos personales previamente identificados se quitan de forma predeterminada de los encabezados en trazas.</span><span class="sxs-lookup"><span data-stu-id="401ff-324">The same rules for hiding potentially personal information in message headers in the previous section apply: the personal information previously identified is removed by default from the headers in traces.</span></span> <span data-ttu-id="401ff-325">El administrador del equipo y el implementador de la aplicación deben modificar la configuración para registrar potencialmente datos personales.</span><span class="sxs-lookup"><span data-stu-id="401ff-325">Both the machine administrator and the application deployer must modify the configuration in order to log potentially personal information.</span></span> <span data-ttu-id="401ff-326">Sin embargo, los datos personales contenidos en encabezados específicos de la aplicación están registrados en trazas.</span><span class="sxs-lookup"><span data-stu-id="401ff-326">However, personal information contained in application-specific headers is logged in traces.</span></span> <span data-ttu-id="401ff-327">El implementador de la aplicación es el responsable de establecer las ACL en los archivos de seguimiento y configuración.</span><span class="sxs-lookup"><span data-stu-id="401ff-327">The application deployer is responsible for setting the ACLs on the configuration and trace files.</span></span> <span data-ttu-id="401ff-328">También puede desactivar la traza si no desea que esta información esté visible, o puede filtrar fuera esta información de los archivos de seguimiento una vez registrado.</span><span class="sxs-lookup"><span data-stu-id="401ff-328">He also can turn off tracing if he does not want this information to be visible, or he can filter out this information from the trace files after it is logged.</span></span>  
  
 <span data-ttu-id="401ff-329">Como parte de la traza de ServiceModel, los id. únicos (llamados id. de actividad y normalmente un GUID) vinculan actividades diferentes juntas como un mensaje fluye a través de diferentes partes de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="401ff-329">As part of ServiceModel Tracing, Unique IDs (called Activity IDs, and typically a GUID) link different activities together as a message flows through different parts of the infrastructure.</span></span>  
  
#### <a name="custom-trace-listeners"></a><span data-ttu-id="401ff-330">Agentes de escucha de traza personalizados</span><span class="sxs-lookup"><span data-stu-id="401ff-330">Custom Trace Listeners</span></span>  
 <span data-ttu-id="401ff-331">Para el registro y la traza de mensajes, se puede configurar un agente de escucha de traza personalizado que puede enviar rastros y mensajes en la conexión (por ejemplo, a una base de datos remota).</span><span class="sxs-lookup"><span data-stu-id="401ff-331">For both message logging and tracing, a custom trace listener can be configured, which can send traces and messages on the wire (for example, to a remote database).</span></span> <span data-ttu-id="401ff-332">El implementador de la aplicación es el responsable de configurar agentes de escucha personalizados o habilitar los usuarios para ello.</span><span class="sxs-lookup"><span data-stu-id="401ff-332">The application deployer is responsible for configuring custom listeners or enabling users to do so.</span></span> <span data-ttu-id="401ff-333">También es responsable de obtener los datos personales expuestos en la ubicación remota y de aplicar correctamente ACL a esta ubicación.</span><span class="sxs-lookup"><span data-stu-id="401ff-333">He is also responsible for any personal information exposed at the remote location, and for properly applying ACLs to this location.</span></span>  
  
### <a name="other-features-for-it-professionals"></a><span data-ttu-id="401ff-334">Otras características para profesionales de TI</span><span class="sxs-lookup"><span data-stu-id="401ff-334">Other features for IT Professionals</span></span>  
 <span data-ttu-id="401ff-335">WCF tiene un proveedor WMI que expone la información de configuración de la infraestructura WCF a través de WMI (incluido con Windows).</span><span class="sxs-lookup"><span data-stu-id="401ff-335">WCF has a WMI provider that exposes the WCF infrastructure configuration information through WMI (shipped with Windows).</span></span> <span data-ttu-id="401ff-336">De forma predeterminada, la interfaz WMI está disponible para los administradores.</span><span class="sxs-lookup"><span data-stu-id="401ff-336">By default, the WMI interface is available to administrators.</span></span>  
  
 <span data-ttu-id="401ff-337">Configuración de WCF utiliza el mecanismo de configuración de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="401ff-337">WCF configuration uses the .NET Framework configuration mechanism.</span></span> <span data-ttu-id="401ff-338">Los archivos de configuración están almacenados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="401ff-338">The configuration files are stored on the machine.</span></span> <span data-ttu-id="401ff-339">El desarrollador de aplicaciones y el administrador crean los archivos de configuración y ACL para cada uno de los requisitos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="401ff-339">The application developer and the administrator create the configuration files and ACL for each of the application's requirements.</span></span> <span data-ttu-id="401ff-340">Un archivo de configuración puede contener las direcciones del extremo y vínculos a los certificados en el almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="401ff-340">A configuration file can contain endpoint addresses and links to certificates in the certificate store.</span></span> <span data-ttu-id="401ff-341">Los certificados se pueden usar para proporcionar los datos de la aplicación con el fin de configurar varias propiedades de las características utilizadas por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="401ff-341">The certificates can be used to provide application data to configure various properties of the features used by the application.</span></span>  
  
 <span data-ttu-id="401ff-342">WCF también usa la funcionalidad de volcado de memoria del proceso de .NET Framework mediante una llamada a la <xref:System.Environment.FailFast%2A> método.</span><span class="sxs-lookup"><span data-stu-id="401ff-342">WCF also uses the .NET Framework process dump functionality by calling the <xref:System.Environment.FailFast%2A> method.</span></span>  
  
### <a name="it-pro-tools"></a><span data-ttu-id="401ff-343">IT Pro Tools</span><span class="sxs-lookup"><span data-stu-id="401ff-343">IT Pro Tools</span></span>  
 <span data-ttu-id="401ff-344">WCF también proporciona las herramientas profesionales de TI siguientes, que se incluyen en el SDK de Windows.</span><span class="sxs-lookup"><span data-stu-id="401ff-344">WCF also provides the following IT professional tools, which ship in the Windows SDK.</span></span>  
  
#### <a name="svctraceviewerexe"></a><span data-ttu-id="401ff-345">SvcTraceViewer.exe</span><span class="sxs-lookup"><span data-stu-id="401ff-345">SvcTraceViewer.exe</span></span>  
 <span data-ttu-id="401ff-346">El visor muestra los archivos de seguimiento WCF.</span><span class="sxs-lookup"><span data-stu-id="401ff-346">The viewer displays WCF trace files.</span></span> <span data-ttu-id="401ff-347">El visor muestra la información cualquier contenida en los seguimientos.</span><span class="sxs-lookup"><span data-stu-id="401ff-347">The viewer shows whatever information is contained in the traces.</span></span>  
  
#### <a name="svcconfigeditorexe"></a><span data-ttu-id="401ff-348">SvcConfigEditor.exe</span><span class="sxs-lookup"><span data-stu-id="401ff-348">SvcConfigEditor.exe</span></span>  
 <span data-ttu-id="401ff-349">El editor permite al usuario crear y editar archivos de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="401ff-349">The editor allows the user to create and edit WCF configuration files.</span></span> <span data-ttu-id="401ff-350">El editor muestra la información cualquier contenida en los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="401ff-350">The editor shows whatever information is contained in the configuration files.</span></span> <span data-ttu-id="401ff-351">La misma tarea se puede lograr con un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="401ff-351">The same task can be accomplished with a text editor.</span></span>  
  
#### <a name="servicemodelreg"></a><span data-ttu-id="401ff-352">ServiceModel_Reg</span><span class="sxs-lookup"><span data-stu-id="401ff-352">ServiceModel_Reg</span></span>  
 <span data-ttu-id="401ff-353">Esta herramienta permite al usuario administrar las instalaciones de ServiceModel en un equipo.</span><span class="sxs-lookup"><span data-stu-id="401ff-353">This tool allows the user to manage ServiceModel installs on a machine.</span></span> <span data-ttu-id="401ff-354">La herramienta muestra los mensajes de estado en una ventana de consola cuando se ejecuta y, en el proceso, puede mostrar información sobre la configuración de la instalación de WCF.</span><span class="sxs-lookup"><span data-stu-id="401ff-354">The tool displays status messages in a console window when it runs and, in the process, may display information about the configuration of the WCF installation.</span></span>  
  
#### <a name="wsatconfigexe-and-wsatuidll"></a><span data-ttu-id="401ff-355">WSATConfig.exe y WSATUI.dll</span><span class="sxs-lookup"><span data-stu-id="401ff-355">WSATConfig.exe and WSATUI.dll</span></span>  
 <span data-ttu-id="401ff-356">Estas herramientas permiten a los profesionales de TI configurar la compatibilidad con la red WS-AtomicTransaction interoperable en WCF.</span><span class="sxs-lookup"><span data-stu-id="401ff-356">These tools allow IT Professionals to configure interoperable WS-AtomicTransaction network support in WCF.</span></span> <span data-ttu-id="401ff-357">Las herramientas muestran y permiten al usuario cambiar los valores de la configuración más utilizada de WS-AtomicTransaction almacenada en el registro.</span><span class="sxs-lookup"><span data-stu-id="401ff-357">The tools display and allow the user to change the values of the most commonly used WS-AtomicTransaction settings stored in the registry.</span></span>  
  
## <a name="cross-cutting-features"></a><span data-ttu-id="401ff-358">Características del corte del cruce</span><span class="sxs-lookup"><span data-stu-id="401ff-358">Cross-cutting Features</span></span>  
 <span data-ttu-id="401ff-359">Las características siguientes son transversales.</span><span class="sxs-lookup"><span data-stu-id="401ff-359">The following features are cross-cutting.</span></span> <span data-ttu-id="401ff-360">Es decir, se pueden crear con cualquiera de las características anteriores.</span><span class="sxs-lookup"><span data-stu-id="401ff-360">That is, they can be composed with any of the preceding features.</span></span>  
  
### <a name="service-framework"></a><span data-ttu-id="401ff-361">Marco de servicios</span><span class="sxs-lookup"><span data-stu-id="401ff-361">Service Framework</span></span>  
 <span data-ttu-id="401ff-362">Los encabezados pueden contener un id. de instancia, que es un GUID que asocia un mensaje a una instancia de una clase CLR.</span><span class="sxs-lookup"><span data-stu-id="401ff-362">Headers can contain an instance ID, which is a GUID that associates a message with an instance of a CLR class.</span></span>  
  
 <span data-ttu-id="401ff-363">El Lenguaje de descripción de servicios Web (WSDL) contiene una definición del puerto.</span><span class="sxs-lookup"><span data-stu-id="401ff-363">The Web Services Description Language (WSDL) contains a definition of the port.</span></span> <span data-ttu-id="401ff-364">Cada puerto tiene una dirección del extremo y un enlace que representa los servicios utilizados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="401ff-364">Each port has an endpoint address and a binding that represents the services used by the application.</span></span> <span data-ttu-id="401ff-365">Exponer WSDL se puede desactivar utilizando la configuración.</span><span class="sxs-lookup"><span data-stu-id="401ff-365">Exposing WSDL can be turned off using configuration.</span></span> <span data-ttu-id="401ff-366">No se retiene información en el equipo.</span><span class="sxs-lookup"><span data-stu-id="401ff-366">No information is retained on the machine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="401ff-367">Vea también</span><span class="sxs-lookup"><span data-stu-id="401ff-367">See also</span></span>
- [<span data-ttu-id="401ff-368">Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="401ff-368">Windows Communication Foundation</span></span>](index.md)
- [<span data-ttu-id="401ff-369">Seguridad</span><span class="sxs-lookup"><span data-stu-id="401ff-369">Security</span></span>](../../../docs/framework/wcf/feature-details/security.md)
