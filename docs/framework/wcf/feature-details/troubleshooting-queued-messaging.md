---
title: "Soluci&#243;n de problemas de la mensajer&#237;a en cola | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a5f2836f-018d-42f5-a571-1e97e64ea5b0
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# Soluci&#243;n de problemas de la mensajer&#237;a en cola
Esta sección contiene preguntas comunes y solución de problemas para utilizar las colas en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
## Preguntas comunes  
 **P:** He usado [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Beta 1 e instalé la revisión de MSMQ.¿Debo quitar la revisión?  
  
 **R:** Sí.Esta revisión ya no se admite.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ahora funciona en MSMQ sin un requisito de revisión.  
  
 **P:** Hay dos enlaces para MSMQ: <xref:System.ServiceModel.NetMsmqBinding> y <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.¿Qué debería utilizar y cuándo?  
  
 **R:** Use <xref:System.ServiceModel.NetMsmqBinding> cuando desee usar MSMQ como transporte para la comunicación en cola entre dos aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Utilice <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> cuando desee utilizar aplicaciones MSMQ existentes para comunicarse con nuevas aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 **P:** ¿Tengo que actualizar MSMQ para usar los enlaces <xref:System.ServiceModel.NetMsmqBinding> y `MsmqIntegration`?  
  
 **R:** No.Ambos enlaces funcionan con MSMQ 3.0 en [!INCLUDE[wxp](../../../../includes/wxp-md.md)] y [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].Ciertas características de los enlaces se vuelven disponibles al actualizar a MSMQ 4.0 en [!INCLUDE[wv](../../../../includes/wv-md.md)].  
  
 **P:** ¿Qué características de los enlaces <xref:System.ServiceModel.NetMsmqBinding> y <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> están disponibles en MSMQ 4.0 pero no en MSMQ 3.0?  
  
 **R:** Las características siguientes están disponibles en MSMQ 4.0 pero no en MSMQ 3.0:  
  
-   La cola de mensajes no enviados personalizada solo se admite en MSMQ 4.0.  
  
-   MSMQ 3.0 y 4.0 controlan los mensajes dudosos de manera diferente.  
  
-   Solo MSMQ 4.0 admite la lectura de transacción remota.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Diferencias en las características de cola en Windows Vista, Windows Server 2003 y Windows XP](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md).  
  
 **P:** ¿Puedo usar MSMQ 3.0 en un lado de una comunicación en cola y MSMQ 4.0 en el otro lado?  
  
 **R:** Sí.  
  
 **P:** Deseo integrar aplicaciones MSMQ existentes con nuevos clientes o servidores [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].¿Necesito actualizar ambos lados de mi infraestructura de MSMQ?  
  
 **R:** No.No tiene que actualizarse a MSMQ 4.0 en ningún lado.  
  
## Solución de problemas  
 Esta sección contiene las respuestas a la mayoría de problemas más comunes.Algunos problemas que son limitaciones conocidas también se describen en las notas de la versión.  
  
 **P:** Estoy intentando usar una cola privada y obtengo la excepción siguiente: `System.InvalidOperationException`: la dirección URL no es válida.La dirección URL para la cola no puede contener el carácter '$'.Utilice la sintaxis en net.msmq:\/\/machine\/private\/queueName para direccionar una cola privada.  
  
 **R:** Compruebe el identificador uniforme de recursos \(URI\) en la configuración y en el código.No utilice el carácter "$" en el URI.Por ejemplo, para direccionar una cola privada denominada OrdersQueue, especifique el URI como net.msmq:\/\/localhost\/private\/ordersQueue.  
  
 **P:** Al llamar a `ServiceHost.Open()` en mi aplicación en cola, se produce la excepción siguiente: `System.ArgumentException`: una dirección base no puede contener una cadena de consulta de URI.¿Por qué?  
  
 **R:** Compruebe el URI de la cola en su archivo de configuración y en el código.Mientras que las colas de MSMQ admiten el uso del carácter "?", los URI lo interpretan como el principio de una consulta de cadena.Para evitar este problema, use nombres de cola que no contengan el carácter "?".  
  
 **P:** Mi envío se realizó correctamente pero en el receptor no se invoca ninguna operación de servicio.¿Por qué?  
  
 **R:** Para determinar la respuesta, use la lista de comprobación siguiente:  
  
-   Compruebe que los requisitos de cola transaccional sean compatibles con las convicciones especificadas.Tenga en cuenta los principios siguientes:  
  
    -   Puede enviar mensajes duraderos \(datagramas y sesiones\) con "exactamente una" convicción \(<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> \= `true`\) solo a una cola transaccional.  
  
    -   Solo puede enviar las sesiones con "exactamente una" convicción.  
  
    -   Se requiere una transacción para recibir mensajes en una sesión de una cola transaccional.  
  
    -   Puede enviar o recibir los mensajes volátiles o duraderos \(solo datagramas\) sin convicciones \(<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> \= `false`\) solo a una cola no transaccional.  
  
-   Compruebe la cola de mensajes no enviados.Si encuentra los mensajes allí, determine por qué no se entregaron.  
  
-   Compruebe la conectividad o los problemas de direccionamiento de las colas de salida.  
  
 **P:** He especificado una cola de mensajes no enviados personalizada, pero cuando inicio la aplicación emisora, se produce una excepción conforme a que no se encuentra la cola de mensajes no enviados o la aplicación emisora no tiene permiso para obtener acceso a la cola de mensajes no enviados.¿Por qué está sucediendo esto?  
  
 **R:** El URI de la cola de mensajes no enviados personalizada debe incluir un "host local" o el nombre de equipo en el primer segmento; por ejemplo, net.msmq:\/\/localhost\/private\/cola de mensajes no enviados de mi aplicación.  
  
 **P:** ¿Siempre es necesario definir una cola de mensajes no enviados personalizada o hay una cola de mensajes no enviados predeterminada?  
  
 **R:** Si la convicción es "exactamente una vez" \(<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> \= `true`\) y si no se especifica una cola de mensajes no enviados personalizada, el valor predeterminado es una cola de mensajes no enviados transaccional para todo el sistema.  
  
 Si no hay convicciones \(<xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> \= `false`\), el valor predeterminado es la ausencia de funcionalidad de cola de mensajes no enviados.  
  
 **P:** Mi servicio inicia SvcHost.Open con un mensaje que afirma que ListenerFactory no puede cumplir los requisitos de EndpointListener.¿Por qué?  
  
 R.Compruebe su contrato de servicio.Quizás haya olvidado colocar "IsOneWay \=`true`" en todas las operaciones del servicio.Las colas solo admiten las operaciones de servicio unidireccionales.  
  
 **P:** Hay mensajes en la cola pero no se invoca ninguna operación de servicio.¿Cuál es el problema?  
  
 **R:** Determine si el host de servicio funciona correctamente.Lo puede comprobar examinando el seguimiento o implementando `IErrorHandler`.El host de servicio, de forma predeterminada, tiene errores si se detecta un mensaje dudoso.  
  
 **P:** Hay mensajes en la cola pero no se activa mi servicio en cola hospedado en web.¿Por qué?  
  
 **R:** La razón más común son los permisos.  
  
1.  Asegúrese de que el proceso `NetMsmqActivator` se esté ejecutando y la identidad del proceso `NetMsmqActivator` se lea y busque el permiso en la cola.  
  
2.  Si `NetMsmqActivator` está supervisando las colas en un equipo remoto, asegúrese de que `NetMsmqActivator` no se ejecute con un token restringido.Para ejecutar `NetMsmqActivator` con un token sin restricciones:  
  
    ```  
    sc sidtype NetMsmqActivator unrestricted  
    ```  
  
 Para problemas de hospedaje en web no relacionados con la seguridad, haga referencia a: [Alojamiento web de una aplicación en cola](../../../../docs/framework/wcf/feature-details/web-hosting-a-queued-application.md).  
  
 **P:** ¿Cuál es la manera más fácil de tener acceso a las sesiones?  
  
 **R:** Establezca AutoComplete\=`true` en la operación que se corresponda con el último mensaje de la sesión y establezca AutoComplete\=`false` en todas las operaciones de servicio restantes.  
  
 **P:** ¿Dónde puedo encontrar respuestas a las dudas habituales sobre MSMQ?  
  
 **R:** [!INCLUDE[crabout](../../../../includes/crabout-md.md)] MSMQ, consulte [Microsoft Message Queuing](http://go.microsoft.com/fwlink/?LinkId=87810).  
  
 **P:** ¿Por qué mi servicio inicia una excepción `ProtocolException` cuándo lee en una cola que contiene mensajes de sesión en cola y mensajes de datagrama en cola?  
  
 **R:** Hay una diferencia fundamental en forma en que se componen los mensajes de sesión en cola y los mensajes de datagrama en cola.Debido a esto, un servicio que está esperando leer un mensaje de la sesión en cola no puede recibir un mensaje del datagrama en cola y un servicio que espera leer un mensaje del datagrama en cola no puede recibir un mensaje de la sesión.Intentar leer ambos tipos de mensajes de la misma cola provoca la excepción siguiente:  
  
```  
System.ServiceModel.MsmqPoisonMessageException: The transport channel detected a poison message. This occurred because the message exceeded the maximum number of delivery attempts or because the channel detected a fundamental problem with the message. The inner exception may contain additional information.   
---> System.ServiceModel.ProtocolException: An incoming MSMQ message contained invalid or unexpected .NET Message Framing information in its body. The message cannot be received. Ensure that the sender is using a compatible service contract with a matching SessionMode.  
```  
  
 La cola de mensajes no enviados del sistema, así como cualquier cola de mensajes no enviados personalizada, es particularmente susceptible a este problema si una aplicación envía mensajes de la sesión en cola y mensajes del datagrama en cola desde el mismo equipo.Si no se puede enviar un mensaje correctamente, se mueve a la cola de mensajes no enviados.Bajo estas circunstancias, es posible tener mensajes de sesión y datagrama en la cola de mensajes no enviados.No hay ninguna manera de separar ambos tipos de mensajes en el tiempo de ejecución al leer de una cola, por consiguiente, las aplicaciones no deberían enviar mensajes de la sesión en cola y mensajes del datagrama en cola desde el mismo equipo.  
  
### Integración de MSMQ: Solución de problemas específicos  
 **P:** Cuando envío un mensaje o cuando abro el host de servicio obtengo un error que indica que el esquema es erróneo.¿Por qué?  
  
 **R:** Al usar el enlace de integración de MSMQ, debe usar el esquema msmq.formatname.Por ejemplo, msmq.formatname:DIRECT\=OS:.\\private$\\OrdersQueue.Pero al especificar la cola de mensajes no enviados personalizada, debe utilizar el esquema de net.msmq.  
  
 **P:** Cuando uso un nombre de formato público o privado y abro el host de servicio en [!INCLUDE[wv](../../../../includes/wv-md.md)], obtengo un error.¿Por qué?  
  
 **R:** El canal de integración [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en [!INCLUDE[wv](../../../../includes/wv-md.md)] comprueba si se puede abrir una subcola para la cola principal de la aplicación con el fin de administrar los mensajes dudosos.El nombre de la subcola se deriva de un URI de msmq.formatname pasado a la escucha.El nombre de la subcola en MSMQ solo puede ser un nombre de formato directo.Aquí radica el error.Cambie el URI de la cola a un nombre de formato directo.  
  
 **P:** Al recibir un mensaje de una aplicación MSMQ, éste permanece en la cola y la aplicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] receptora no lo lee.¿Por qué?  
  
 **R:** Compruebe si el mensaje tiene cuerpo.Si el mensaje no tiene ningún cuerpo, el canal de integración de MSMQ omite el mensaje.Implemente `IErrorHandler` para recibir notificaciones de las excepciones y comprobar las trazas.  
  
### Solución de problemas relacionados con la seguridad  
 **P:** Cuando ejecuto el ejemplo que usa un enlace predeterminado en modo de grupo de trabajo, los mensajes parecen enviarse pero nunca se reciben.  
  
 **R:** De forma predeterminada, los mensajes se firman con un certificado interno de MSMQ que requiere el servicio de directorio Active Directory.En modo del grupo de trabajo, puesto que Active Directory no está disponible, la firma de los mensajes falla.Así que el mensaje aterriza en la cola de mensajes no enviados y provoca el error, como "Firma no válida".  
  
 La solución alternativa es desactivar la seguridad.Esto se hace estableciendo <xref:System.ServiceModel.NetMsmqSecurity.Mode%2A> \= <xref:System.ServiceModel.NetMsmqSecurityMode> para que funcione en modo de grupo de trabajo.  
  
 Otra solución alternativa es recibir <xref:System.ServiceModel.MsmqTransportSecurity> de la propiedad <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A> y establecerlo en <xref:System.ServiceModel.MsmqAuthenticationMode>y establecer el certificado de cliente.  
  
 Todavía otra solución alternativa es instalar MSMQ con integración de Active Directory.  
  
 **P:** Cuando envío un mensaje con enlace predeterminado \(seguridad de transporte activada\) en Active Directory a una cola, obtengo un mensaje que indica que no se encuentra el certificado interno.¿Cómo se soluciona?  
  
 **R:** Esto significa que se debe renovar el certificado del remitente en Active Directory.Para hacerlo, abra **Panel de control**, **Herramientas administrativas**, **Administración de equipos**, haga clic con el botón secundario en **MSMQ**y selecciona **Propiedades**.Seleccione la pestaña **Certificado de usuario** y haga clic en el botón **Renovar**.  
  
 **P:** Cuando envío un mensaje mediante <xref:System.ServiceModel.MsmqAuthenticationMode> y especifico el certificado que se va a usar, aparece un mensaje de error que indica que el certificado no es válido.¿Cómo se soluciona?  
  
 **R:** No puede usar un almacén de certificados del equipo local en modo de certificado.Tiene que copiar el certificado del almacén de certificados del equipo al almacén del usuario actual utilizando el complemento del certificado.Para obtener el complemento del certificado:  
  
1.  Haga clic en **Inicio**, seleccione **Ejecutar**, escriba `mmc`, y haga clic en **Aceptar**.  
  
2.  En la **Microsoft Management Console**, abra el menú **Archivo** y seleccione **Agregar\/quitar complemento**.  
  
3.  En el cuadro de diálogo **Agregar\/quitar complemento**, haga clic en el botón **Agregar**.  
  
4.  En el cuadro de diálogo **Agregar un complemento independiente**, seleccione Certificados y haga clic en **Agregar**.  
  
5.  En el cuadro de diálogo del complemento **Certificados**, seleccione **Mi cuenta de usuario** y haga clic en **Finalizar**.  
  
6.  Luego, agregue un segundo complemento Certificados utilizando los pasos anteriores, pero esta vez seleccione **Cuenta de equipo** y haga clic en **Siguiente**.  
  
7.  Seleccione **Equipo local** y haga clic en **Finalizar**.Ahora puede arrastrar y colocar certificados del almacén de certificados del equipo al almacén del usuario actual.  
  
 **P:** Cuando mi servicio lee en una cola en otro equipo en modo de grupo de trabajo, se produce una excepción de acceso denegado.  
  
 **R:** En modo de grupo de trabajo, para que una aplicación remota obtenga acceso a la cola, la aplicación debe tener permiso de acceso a la cola.Agregue "Inicio de sesión anónimo" a la lista de control de acceso de la cola \(ACL\) y proporciónele permiso de lectura.  
  
 **P:** Cuando un cliente del servicio de red \(o cualquier cliente que no tenga una cuenta de dominio\) envía un mensaje en cola, se produce un error en el envío que indica que el certificado no es válido.¿Cómo lo soluciono?  
  
 **R:** Compruebe la configuración del enlace.El enlace predeterminado tiene la seguridad de transporte de MSMQ activada para firmar el mensaje.Desactívela.  
  
### Recepciones de transacción remotas  
 **P:** Cuando tengo una cola en el equipo A y un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que lee los mensajes de una cola en el equipo B \(escenario de recepción de transacción remota\), los mensajes no se leen de la cola.La información de seguimiento indica que hubo un fallo en la recepción con el mensaje “No se puede importar la transacción”. ¿Qué puedo hacer para solucionarlo?  
  
 **R:** Pueden existir tres posibles razones:  
  
-   Si está en modo del dominio, la recepción de transacciones remotas requiere el acceso de red de Microsoft DTC \(Coordinador de transacciones distribuidas\) \(MSDTC\).Puede habilitarlo utilizando **Agregar\/quitar componentes**.  
  
     ![Habilitar acceso a DTC desde la red](../../../../docs/framework/wcf/feature-details/media/applicationserveraddcomps.jpg "ApplicationServerAddComps")  
  
-   Compruebe el modo de autenticación para comunicarse con el administrador de transacciones.Si está en modo de grupo de trabajo, debe seleccionar "No se requiere autenticación".Si está en modo de dominio, debe seleccionar "Autenticación mutua requerida".  
  
     ![Habilitar transacciones XA](../../../../docs/framework/wcf/feature-details/media/4f3695e0-fb0b-4c5b-afac-75f8860d2bb0.jpg "4f3695e0\-fb0b\-4c5b\-afac\-75f8860d2bb0")  
  
-   Asegúrese de que MSDTC esté en la lista de excepciones en la configuración de **Firewall de conexión a Internet**.  
  
-   Asegúrese de que está utilizando [!INCLUDE[wv](../../../../includes/wv-md.md)].MSMQ en [!INCLUDE[wv](../../../../includes/wv-md.md)] admite la lectura de transacciones remotas.MSMQ en versiones anteriores de Windows no admite la lectura de transacciones remotas.  
  
 **P:** Cuando el servicio que lee de la cola es un servicio de red, por ejemplo, en un host de web, ¿por qué obtengo una excepción de acceso denegado al leer de la cola?  
  
 **R:** El acceso de lectura de servicio de red debe agregarse a la cola ACL para garantizar que un servicio de red pueda leer de la cola.  
  
 **P:** ¿Puedo usar el servicio de activación MSMQ para activar aplicaciones basadas en mensajes en una cola en un equipo remoto?  
  
 **R:** Sí.Para ello, debe configurar el servicio de activación de MSMQ para que se ejecute como un servicio de red y agregar el acceso del servicio de red a la cola en el equipo remoto.  
  
## Utilizar los enlaces personalizados de MSMQ con ReceiveContext habilitado  
 Al utilizar un enlace personalizado de MSMQ con <xref:System.ServiceModel.Channels.ReceiveContext> habilitado, al procesar un mensaje entrante se utilizará un subproceso del grupo de subprocesos porque MSMQ nativo no admite la realización de E\/S para recepciones <xref:System.ServiceModel.Channels.ReceiveContext> asincrónicas.Esto se debe a que, al procesar este tipo de mensaje, se utilizan transacciones internas para <xref:System.ServiceModel.Channels.ReceiveContext> y MSMQ no admite el procesamiento asincrónico.Para evitar este problema, puede agregar <xref:System.ServiceModel.Description.SynchronousReceiveBehavior> al extremo para forzar el procesamiento sincrónico, o establecer <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.MaxPendingReceives%2A> en 1.