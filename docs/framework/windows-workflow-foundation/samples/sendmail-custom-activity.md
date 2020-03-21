---
title: Actividad personalizada SendMail
ms.date: 03/30/2017
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
ms.openlocfilehash: e7cc64e68c3d78b9ee7ec813700e96a52c239141
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182779"
---
# <a name="sendmail-custom-activity"></a>Actividad personalizada SendMail
En este ejemplo se muestra cómo crear una actividad personalizada que deriva de <xref:System.Activities.AsyncCodeActivity> para enviar correo utilizando SMTP para el uso dentro de una aplicación de flujo de trabajo. La actividad personalizada utiliza <xref:System.Net.Mail.SmtpClient> las capacidades de enviar correo electrónico de forma asincrónica y enviar correo con autenticación. También proporciona algunas características de usuario final como el modo de prueba, reemplazo del token, plantillas de archivo y ruta de colocación para dejar la prueba.  
  
 En la siguiente tabla se detallan los argumentos de la actividad `SendMail`.  
  
|Nombre|Tipo|Descripción|  
|-|-|-|  
|Host|String|Dirección del host del servidor SMTP.|  
|Port|String|El puerto del servicio SMTP en el host.|  
|EnableSsl|bool|Especifica si el objeto <xref:System.Net.Mail.SmtpClient> utiliza SSL (Secure Sockets Layer) para cifrar la conexión.|  
|UserName|String|Nombre de usuario para preparar las credenciales para autenticar la propiedad <xref:System.Net.Mail.SmtpClient.Credentials%2A> del remitente.|  
|Contraseña|String|Contraseña para preparar las credenciales para autenticar la propiedad <xref:System.Net.Mail.SmtpClient.Credentials%2A> del remitente.|  
|Asunto|<xref:System.Activities.InArgument%601>\<> de cuerdas|Asunto del mensaje.|  
|Body|<xref:System.Activities.InArgument%601>\<> de cuerdas|Cuerpo del mensaje.|  
|Datos adjuntos|<xref:System.Activities.InArgument%601>\<> de cuerdas|Colección de datos adjuntos que se usa para almacenar datos adjuntos a este mensaje de correo electrónico.|  
|De|<xref:System.Net.Mail.MailAddress>|Desde la dirección de este mensaje de correo electrónico.|  
|A|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Colección de direcciones que contiene los destinatarios de este mensaje de correo electrónico.|  
|CC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Colección de direcciones que contiene los destinatarios de la copia de carbono (CC) para este mensaje de correo electrónico.|  
|BCC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Colección de direcciones que contiene los destinatarios de la copia de carbón ciego (BCC) para este mensaje de correo electrónico.|  
|Tokens|<xref:System.Activities.InArgument%601><cadena\<IDictionary, cadena>>|Tokens para reemplazar en el cuerpo. Esta característica les permite a los usuarios especificar algunos valores del cuerpo que pueden ser reemplazados después por los tokens que proporcionó utilizando esta propiedad.|  
|BodyTemplateFilePath|String|Ruta de acceso de una plantilla para el cuerpo. La actividad `SendMail` copia el contenido de este archivo en su propiedad de cuerpo.<br /><br /> La plantilla puede contener tokens que son reemplazados por el contenido de la propiedad de tokens.|  
|TestMailTo|<xref:System.Net.Mail.MailAddress>|Cuando se establece esta propiedad, todos los correos electrónicos se envían a la dirección especificada en ella.<br /><br /> Se pretende que esta propiedad sea utilizada al probar los flujos de trabajo. Por ejemplo, cuando desee asegurarse de que todos los correos electrónicos se envían sin enviarlos a los destinatarios reales.|  
|TestDropPath|String|Cuando se establece esta propiedad, todos los correos electrónicos también se guardan en el archivo especificado.<br /><br /> Esta propiedad está diseñada para usarse al probar o depurar flujos de trabajo, para asegurarse de que el formato y el contenido de los correos electrónicos salientes son adecuados.|  
  
## <a name="solution-contents"></a>Contenido de la solución  
 La solución contiene dos proyectos.  
  
|proyecto|Descripción|Archivos importantes|  
|-------------|-----------------|---------------------|  
|SendMail|La actividad SendMail|1. SendMail.cs: implementación de la actividad principal<br />2. SendMailDesigner.xaml y SendMailDesigner.xaml.cs: diseñador para la actividad SendMail<br />3. MailTemplateBody.htm: plantilla para el correo electrónico que se va a enviar.|  
|SendMailTestClient|Cliente para probar la actividad SendMail.  Este proyecto muestra dos maneras de invocar la actividad SendMail: mediante declaración y mediante programación.|1. Sequence1.xaml: flujo de trabajo que invoca la actividad SendMail.<br />2. Program.cs: invoca Sequence1 y también crea un flujo de trabajo mediante programación que utiliza SendMail.|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a>Nueva configuración de la actividad SendMail  
 Aunque no se muestra en el ejemplo, los usuarios pueden realizar una configuración adicional de la actividad SendMail. Las tres secciones siguientes muestran cómo se hace esto.  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a>Enviar un correo electrónico mediante los tokens especificados en el cuerpo  
 Este fragmento de código muestra cómo puede enviar el correo electrónico con tokens en el cuerpo. Observe que los tokens se proporcionan en la propiedad del cuerpo. Los valores para esos tokens se proporcionan a la propiedad de tokens.  
  
```csharp  
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
  
### <a name="sending-an-email-using-a-template"></a>Enviar un correo electrónico mediante una plantilla  
 Este fragmento de código muestra cómo enviar un correo electrónico utilizando tokens de la plantilla en el cuerpo. Observe que al establecer la propiedad `BodyTemplateFilePath` no necesitamos proporcionar el valor de la propiedad Body (el contenido del archivo de plantilla se copiará en el cuerpo).  
  
```csharp  
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
  
### <a name="sending-mails-in-testing-mode"></a>Enviar correo en modo de prueba  
 Este fragmento de código muestra cómo establecer `TestMailTo` las dos propiedades de `john.doe@contoso.con` prueba: estableciendo en todos los mensajes se enviará a (sin tener en cuenta los valores de Para, CC, CCO). Estableciendo que todos los correos electrónicos de salida a TestDropPath se registrarán también en la ruta de acceso proporcionada. Estas propiedades se pueden establecer independientemente (no están relacionadas).  
  
```csharp  
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
  
## <a name="set-up-instructions"></a>Instrucciones de instalación  
 En este ejemplo se requiere acceso a un servidor SMTP.  
  
 Para obtener más información acerca de la configuración de un servidor SMTP, consulte los vínculos siguientes.  
  
- [Configurar el servicio SMTP (IIS 6.0)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc784968(v=ws.10))  
  
- [IIS 7.0: configurar correo electrónico de SMTP](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772058(v=ws.10))  
  
- [Cómo instalar el servicio SMTP](https://docs.microsoft.com/previous-versions/tn-archive/aa997480(v=exchg.65))  
  
 Hay disponibles para descarga emuladores de SMTP proporcionados por terceros.  
  
##### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo  
  
1. Con Visual Studio 2010, abra el archivo de solución SendMail.sln.  
  
2. Asegúrese de que tiene acceso a un servidor SMTP válido. Vea las instrucciones de configuración.  
  
3. Configure el programa con la dirección del servidor y las direcciones de correo electrónico Desde y Hasta.  
  
     Para ejecutar correctamente este ejemplo, es posible que deba configurar el valor de las direcciones de correo electrónico From y To y la dirección del servidor SMTP en Program.cs y en Sequence.xaml. Necesitará cambiar la dirección en ambas ubicaciones, dado que el programa envía el correo de dos maneras diferentes  
  
4. Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
5. Para ejecutar la solución, presione CTRL+F5.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`
