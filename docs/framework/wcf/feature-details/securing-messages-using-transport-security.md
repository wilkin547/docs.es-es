---
title: "Protecci&#243;n de mensajes utilizando la seguridad de transporte | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9029771a-097e-448a-a13a-55d2878330b8
caps.latest.revision: 21
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 21
---
# Protecci&#243;n de mensajes utilizando la seguridad de transporte
En esta sección se discute la seguridad de transporte de Message Queuing \(MSMQ\) que puede utilizar para proteger los mensajes enviados a una cola.  
  
> [!NOTE]
>  Antes de leer este tema, se recomienda que lea [Conceptos de seguridad](../../../../docs/framework/wcf/feature-details/security-concepts.md).  
  
 La ilustración siguiente proporciona un modelo conceptual de comunicación en cola utilizando [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].La ilustración y la terminología se utilizan para explicar los conceptos de la seguridad de transporte.  
  
 ![Diagrama de aplicaciones puestas en cola](../../../../docs/framework/wcf/feature-details/media/distributed-queue-figure.jpg "Distributed\-Queue\-Figure")  
  
 Al enviar mensajes en cola utilizando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con <xref:System.ServiceModel.NetMsmqBinding>, el mensaje [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] está adjunto como un cuerpo del mensaje de MSMQ.La seguridad de transporte protege el mensaje de MSMQ completo \(encabezados del mensaje de MSMQ o propiedades y el cuerpo del mensaje\).Dado que es el cuerpo del mensaje de MSMQ, al utilizar la seguridad de transporte también se protege el mensaje [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 El concepto clave detrás de la seguridad de transporte es que el cliente tiene que cumplir los requisitos de seguridad para obtener el mensaje en la cola de destino.Esto es diferente de la seguridad del mensaje, donde el mensaje se protege para la aplicación que recibe el mensaje.  
  
 La seguridad de transporte utilizando <xref:System.ServiceModel.NetMsmqBinding> y <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> impacta en cómo los mensajes de MSMQ se protegen en tránsito entre la cola de transmisión y la cola de destino donde estar protegido implica:  
  
-   Firmar el mensaje para asegurarse que no está manipulado.  
  
-   Cifrar el mensaje para asegurarse que no se pueda ver o manipular.Esto se recomienda pero es opcional.  
  
-   El administrador de la cola de destino que identifica el remitente del mensaje para no rechazarlo.  
  
 En MSMQ, independiente de la autenticación, la cola de destino tiene una lista de control de acceso \(ACL\) para comprobar si el cliente tiene el permiso para enviar el mensaje a la cola de destino.También se comprueba que la aplicación receptora tenga permiso para recibir el mensaje de la cola de destino.  
  
## Propiedades de la seguridad de transporte WCF MSMQ  
 MSMQ utiliza la seguridad de Windows para la autenticación.Utiliza el identificador de seguridad de Windows \(SID\) para identificar el cliente y utiliza el servicio de directorio Active Directory como la entidad de certificación al autenticar el cliente.Esto exige que MSMQ se instale con integración de Active Directory.Puesto que el SID del dominio de Windows se utiliza para identificar el cliente, esta opción de seguridad solo es significativa cuando tanto el cliente como el servicio forman parte del mismo dominio de Windows.  
  
 MSMQ también proporciona la capacidad de adjuntar un certificado con el mensaje que no está registrado con Active Directory.En este caso, garantiza que el mensaje se firmó utilizando el certificado adjunto.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona ambas opciones como parte de la seguridad de transporte de MSMQ y son el eje clave para la seguridad de transporte.  
  
 De forma predeterminada, la seguridad de transporte está activada.  
  
 Teniendo en cuenta estas cuestiones básicas, las secciones siguientes detallan propiedades de seguridad de transporte incluidas con <xref:System.ServiceModel.NetMsmqBinding> y <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.  
  
#### Modo de autenticación MSMQ  
 <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> dicta si utilizar la seguridad de dominio de Windows o una seguridad externa basada en certificado para proteger el mensaje.En ambos modos de autenticación, el canal de transporte en cola [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza el `CertificateValidationMode` especificado en la configuración de servicio.El modo de validación de certificado especifica el mecanismo utilizado para comprobar la validez del certificado.  
  
 Cuando la seguridad de transporte está activada, la configuración predeterminada es <xref:System.ServiceModel.MsmqAuthenticationMode>.  
  
#### Modo de autenticación del dominio Windows  
 La opción de usar la seguridad de Windows necesita la integración de Active Directory.<xref:System.ServiceModel.MsmqAuthenticationMode> es el modo de seguridad de transporte predeterminado.Cuando está establecido, el canal [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]adjunta el SID de Windows al mensaje de MSMQ y usa su certificado interno obtenido de Active Directory.MSMQ utiliza este certificado interno para proteger el mensaje.El administrador de la cola receptora utiliza Active Directory para buscar y encontrar un certificado correspondiente para autenticar el cliente y comprueba que el SID también coincida con el del cliente.Este paso de autenticación se ejecuta si un certificado, generado internamente en el caso de modo de autenticación `WindowsDomain` o generado externamente en el caso de modo de autenticación `Certificate`, está adjunto al mensaje aun cuando la cola de destino no esté marcada como autenticación necesaria.  
  
> [!NOTE]
>  Al crear una cola, puede marcar la cola como una cola autenticada para indicar que la cola requiere autenticación del cliente que envía los mensajes a la cola.Esto garantiza que no se acepte ningún mensaje no autenticado en la cola.  
  
 El SID adjunto con el mensaje también se utiliza para compararlo con el ACL de la cola de destino para asegurarse de que el cliente tenga la autoridad para enviar los mensajes a la cola.  
  
#### Modo de autenticación de certificados  
 La opción de utilizar el modo de autenticación del certificado no requiere la integración de Active Directory.De hecho, en algunos casos, como cuando MSMQ se instala en modo de grupo de trabajo \(sin la integración de Active Directory\) o al utilizar el protocolo de transferencia SOAP Reliable Messaging Protocol \(SRMP\) para enviar los mensajes a la cola, solo <xref:System.ServiceModel.MsmqAuthenticationMode> funciona.  
  
 Al enviar un mensaje [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con <xref:System.ServiceModel.MsmqAuthenticationMode>, el canal [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no agrega un SID de Windows al mensaje de MSMQ.Como a tal, el ACL de la cola de destino debe a `Anonymous` acceso de usuario para realizar envíos a la cola.El administrador de la cola receptora comprueba si el mensaje de MSMQ se firmó con el certificado pero no realiza ninguna autenticación.  
  
 El certificado con sus notificaciones e información de identidad es rellenado en <xref:System.ServiceModel.ServiceSecurityContext> por el canal de transporte en cola [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].El servicio puede utilizar esta información para realizar su propia autenticación del remitente.  
  
### Nivel de protección de MSMQ  
 El nivel de protección dicta cómo proteger el mensaje de MSMQ para garantizar que no se manipule.Se especifica en la propiedad <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>.El valor predeterminado es <xref:System.Net.Security.ProtectionLevel>.  
  
#### Nivel de protección de firma  
 El mensaje de MSMQ se firma utilizando el certificado generado internamente al utilizar modo de autenticación `WindowsDomain` o un certificado generado externamente al utilizar el modo de autenticación `Certificate`.  
  
#### Nivel de protección de firma y cifrado  
 El mensaje de MSMQ se firma utilizando el certificado generado internamente al utilizar el modo de autenticación `WindowsDomain` o el certificado generado externamente al utilizar el modo de autenticación `Certificate`.  
  
 Además de la firma del mensaje, el mensaje de MSMQ se cifra utilizando la clave pública del certificado obtenido de Active Directory que pertenece al administrador de la cola receptora que hospeda la cola de destino.El administrador de la cola emisora garantiza que el mensaje de MSMQ esté cifrado en tránsito.El administrador de la cola receptora descifra el mensaje de MSMQ mediante la clave privada de su certificado interno y almacena el mensaje en la cola \(si se autentica y autoriza\) en texto no cifrado.  
  
> [!NOTE]
>  Para cifrar el mensaje, se requiere acceso a Active Directory \(la propiedad `UseActiveDirectory` de <xref:System.ServiceModel.NetMsmqBinding> debe estar establecida en `true`\) y se puede utilizar tanto con <xref:System.ServiceModel.MsmqAuthenticationMode> como <xref:System.ServiceModel.MsmqAuthenticationMode>.  
  
#### Ningún nivel de protección  
 Esto sucede cuando <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> está establecido en <xref:System.Net.Security.ProtectionLevel>.Éste no puede ser un valor válido para cualquier otro modo de autenticación.  
  
> [!NOTE]
>  Si el mensaje de MSMQ está firmado, MSMQ comprueba si el mensaje está firmado con el certificado adjunto \(interno o externo\) independiente del estado de la cola, es decir, cola autenticada o no.  
  
### Algoritmo de cifrado de MSMQ  
 El algoritmo de cifrado especifica el algoritmo a utilizar para cifrar el mensaje MSMQ durante la conexión.Esta propiedad solo se utiliza si <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> se define como <xref:System.Net.Security.ProtectionLevel>.  
  
 Los algoritmos soportados son `RC4Stream` y `AES` y el valor predeterminado es `RC4Stream`.  
  
 Solo puede utilizar el algoritmo `AES` si el remitente tiene MSMQ 4.0 instalado.Además, la cola de destino también debe estar hospedada en MSMQ 4.0.  
  
### Algoritmo hash de MSMQ  
 El algoritmo hash especifica el algoritmo utilizado para crear una firma digital del mensaje de MSMQ.El administrador de la cola receptora utiliza este mismo algoritmo para autenticar el mensaje de MSMQ.Esta propiedad solo se usa si <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> se establece en <xref:System.Net.Security.ProtectionLevel> o <xref:System.Net.Security.ProtectionLevel>.  
  
 Los algoritmos admitidos son `MD5`, `SHA1`, `SHA256` y `SHA512`.El valor predeterminado es `SHA1`.  
  
## Vea también  
 [Message Queuing](http://msdn.microsoft.com/es-es/ff917e87-05d5-478f-9430-0f560675ece1)   
 [Conceptos de seguridad](../../../../docs/framework/wcf/feature-details/security-concepts.md)   
 [Protección de servicios y clientes](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)