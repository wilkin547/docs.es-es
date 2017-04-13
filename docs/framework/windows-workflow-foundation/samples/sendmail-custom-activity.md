---
title: "Actividad personalizada SendMail | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Actividad personalizada SendMail
En este ejemplo se muestra cómo crear una actividad personalizada que deriva de <xref:System.Activities.AsyncCodeActivity> para enviar correo utilizando SMTP para el uso dentro de una aplicación de flujo de trabajo.La actividad personalizada utiliza las capacidades de <xref:System.Net.Mail.SmtpClient> para enviar el correo electrónico de forma asincrónica y enviar el correo con autenticación.También proporciona algunas características de usuario final como el modo de prueba, reemplazo del token, plantillas de archivo y ruta de acceso para dejar la prueba.  
  
 En la siguiente tabla se detallan los argumentos de la actividad `SendMail`.  
  
||||  
|-|-|-|  
|Nombre|Tipo|Descripción|  
|Host|String|Dirección del host del servidor SMTP.|  
|Port|String|El puerto del servicio SMTP en el host.|  
|EnableSsl|bool|Especifica si el objeto <xref:System.Net.Mail.SmtpClient> utiliza SSL \(Secure Sockets Layer\) para cifrar la conexión.|  
|UserName|String|Nombre de usuario para preparar las credenciales para autenticar la propiedad <xref:System.Net.Mail.SmtpClient.Credentials%2A> del remitente.|  
|Password|String|Contraseña para preparar las credenciales para autenticar la propiedad <xref:System.Net.Mail.SmtpClient.Credentials%2A> del remitente.|  
|Subject|<xref:System.Activities.InArgument%601>\<string\>|Asunto del mensaje.|  
|Body|<xref:System.Activities.InArgument%601>\<string\>|Cuerpo del mensaje.|  
|Attachments|<xref:System.Activities.InArgument%601>\<string\>|Colección de datos adjuntos que se utiliza para almacenar los datos adjuntos a este mensaje de correo electrónico.|  
|From|<xref:System.Net.Mail.MailAddress>|Dirección del remitente de este mensaje de correo electrónico.|  
|To|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>\>|Colección de direcciones que contiene los destinatarios de este mensaje de correo electrónico.|  
|CC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>\>|Colección de direcciones que contiene los destinatarios para recibir copia \(CC\) de este mensaje de correo electrónico.|  
|BCC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>\>|Colección de direcciones que contiene los destinatarios ocultos de copia \(CCO\) de este mensaje de correo electrónico.|  
|Tokens|<xref:System.Activities.InArgument%601>\<IDictionary\<string, string\>\>|Tokens para reemplazar en el cuerpo.Esta característica les permite a los usuarios especificar algunos valores del cuerpo que pueden ser reemplazados después por los tokens que proporcionó utilizando esta propiedad.|  
|BodyTemplateFilePath|String|Ruta de acceso de una plantilla para el cuerpo.La actividad `SendMail` copia el contenido de este archivo en su propiedad de cuerpo.<br /><br /> La plantilla puede contener tokens que son reemplazados por el contenido de la propiedad de tokens.|  
|TestMailTo|<xref:System.Net.Mail.MailAddress>|Cuando se establece esta propiedad, todos los correo electrónicos se envían a la dirección especificada en él.<br /><br /> Se pretende que esta propiedad sea utilizada al probar los flujos de trabajo.Por ejemplo, cuando desea asegurarse de que todos los correo electrónicos se envíen sin enviarlos a los destinatarios reales.|  
|TestDropPath|String|Cuando se establece esta propiedad, todos los correos electrónicos se guardan también en el archivo especificado.<br /><br /> Se pretende que esta propiedad sea utilizada cuando prueba o depura flujos de trabajo, para asegurarse de que el formato y contenido de los mensajes de correo electrónico salientes son adecuados.|  
  
## Contenido de la solución  
 La solución contiene dos proyectos.  
  
|Proyecto|Descripción|Archivos importantes|  
|--------------|-----------------|--------------------------|  
|SendMail|La actividad SendMail|1.  SendMail.cs: implementación para la actividad principal<br />2.  SendMailDesigner.xaml y SendMailDesigner.xaml.cs: diseñador para la actividad SendMail<br />3.  MailTemplateBody.htm: la plantilla para el correo electrónico que se va a enviar.|  
|SendMailTestClient|Cliente para probar la actividad SendMail.Este proyecto muestra dos maneras de invocar la actividad SendMail: mediante declaración y mediante programación.|1.  Sequence1.xaml: flujo de trabajo que invoca la actividad SendMail.<br />2.  Program.cs: invoca Sequence1 y también crea un flujo de trabajo mediante programación que utiliza SendMail.|  
  
## Nueva configuración de la actividad SendMail  
 Aunque no se muestra en el ejemplo, los usuarios pueden realizar una configuración adicional de la actividad SendMail.Las tres secciones siguientes muestran cómo se hace esto.  
  
### Enviar un correo electrónico mediante los tokens especificados en el cuerpo  
 Este fragmento de código muestra cómo puede enviar el correo electrónico con tokens en el cuerpo.Observe que los tokens se proporcionan en la propiedad del cuerpo.Los valores para esos tokens se proporcionan a la propiedad de tokens.  
  
```html  
IDictionary<string, string> tokens = new Dictionary<string, string>();  
tokens.Add("@name", "John Doe");  
tokens.Add("@date", DateTime.Now.ToString());  
tokens.Add("@server", "localhost");  
  
new SendMail  
{  
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Body = "Hello @name. This is a test email sent from @server. Current date is @date",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens)  
};  
  
```  
  
### Enviar un correo electrónico mediante una plantilla  
 Este fragmento de código muestra cómo enviar un correo electrónico utilizando tokens de la plantilla en el cuerpo.Observe que al establecer la propiedad `BodyTemplateFilePath` no necesitamos proporcionar el valor de la propiedad Body \(el contenido del archivo de plantilla se copiará en el cuerpo\).  
  
```  
new SendMail  
{    
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
    BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",   
};  
  
```  
  
### Enviar correo en modo de prueba  
 Este fragmento de código muestra cómo establecer las dos propiedades de prueba: estableciendo `TestMailTo` en todos los mensajes se enviará a john.doe@contoso.con \(sin considerar de los valores To, Cc, Bcc\).Estableciendo que todos los correos electrónicos de salida a TestDropPath se registrarán también en la ruta de acceso proporcionada.Estas propiedades se pueden establecer independientemente \(no están relacionadas\).  
  
```  
new SendMail  
{    
   From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
   Subject = "Test email",  
   Host = "localhost",  
   Port = 25,  
   Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
   BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",  
   TestMailTo= new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   TestDropPath = @"c:\Samples\SendMail\TestDropPath\",  
};  
  
```  
  
## Instrucciones de instalación  
 En este ejemplo se requiere acceso a un servidor SMTP.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]que prepara un servidor SMTP, vea los siguientes vínculos.  
  
-   [Microsoft Technet](http://go.microsoft.com/fwlink/?LinkId=166060)  
  
-   [Configurar el servicio SMTP \(IIS 6.0\)](http://go.microsoft.com/fwlink/?LinkId=150456)  
  
-   [IIS 7.0: configurar correo electrónico de SMTP](http://go.microsoft.com/fwlink/?LinkId=150457)  
  
-   [Cómo instalar el servicio SMTP](http://go.microsoft.com/fwlink/?LinkId=150458)  
  
 Hay disponibles para descarga emuladores de SMTP proporcionados por terceros.  
  
##### Para ejecutar este ejemplo  
  
1.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución SendMail.sln de la solución.  
  
2.  Asegúrese de que tiene acceso a un servidor SMTP válido.Vea las instrucciones de configuración.  
  
3.  Configure el programa con su dirección de servidor y las direcciones de correo electrónico From y To.  
  
     Para ejecutar este ejemplo correctamente, puede necesitar configurar el valor de las direcciones de correo electrónico From y To, y la dirección del servidor SMTP, en Program.cs y en Sequence.xaml.Necesitará cambiar la dirección en ambas ubicaciones, dado que el programa envía el correo de dos maneras diferentes  
  
4.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
5.  Para ejecutar la solución, presione CTRL\+F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`  
  
## Vea también