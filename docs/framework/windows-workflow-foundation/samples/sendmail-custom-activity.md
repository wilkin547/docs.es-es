---
title: Actividad personalizada SendMail
ms.date: 03/30/2017
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
ms.openlocfilehash: e9d27711754c3aa8ff7f68c23f528c9f5c4356f7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43423405"
---
# <a name="sendmail-custom-activity"></a><span data-ttu-id="8e5a2-102">Actividad personalizada SendMail</span><span class="sxs-lookup"><span data-stu-id="8e5a2-102">SendMail Custom Activity</span></span>
<span data-ttu-id="8e5a2-103">En este ejemplo se muestra cómo crear una actividad personalizada que deriva de <xref:System.Activities.AsyncCodeActivity> para enviar correo utilizando SMTP para el uso dentro de una aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-103">This sample demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span> <span data-ttu-id="8e5a2-104">La actividad personalizada utiliza las capacidades de <xref:System.Net.Mail.SmtpClient> para enviar correo electrónico de forma asincrónica y enviar correo electrónico con la autenticación.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-104">The custom activity uses the capabilities of <xref:System.Net.Mail.SmtpClient> to send email asynchronously and to send mail with authentication.</span></span> <span data-ttu-id="8e5a2-105">También proporciona algunas características de usuario final como el modo de prueba, reemplazo del token, plantillas de archivo y ruta de colocación para dejar la prueba.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-105">It also provides some end-user features like test mode, token replacement, file templates, and test drop path.</span></span>  
  
 <span data-ttu-id="8e5a2-106">En la siguiente tabla se detallan los argumentos de la actividad `SendMail`.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-106">The following table details the arguments for the `SendMail` activity.</span></span>  
  
|<span data-ttu-id="8e5a2-107">Name</span><span class="sxs-lookup"><span data-stu-id="8e5a2-107">Name</span></span>|<span data-ttu-id="8e5a2-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="8e5a2-108">Type</span></span>|<span data-ttu-id="8e5a2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e5a2-109">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8e5a2-110">Host</span><span class="sxs-lookup"><span data-stu-id="8e5a2-110">Host</span></span>|<span data-ttu-id="8e5a2-111">String</span><span class="sxs-lookup"><span data-stu-id="8e5a2-111">String</span></span>|<span data-ttu-id="8e5a2-112">Dirección del host del servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-112">Address of the SMTP server host.</span></span>|  
|<span data-ttu-id="8e5a2-113">Puerto</span><span class="sxs-lookup"><span data-stu-id="8e5a2-113">Port</span></span>|<span data-ttu-id="8e5a2-114">String</span><span class="sxs-lookup"><span data-stu-id="8e5a2-114">String</span></span>|<span data-ttu-id="8e5a2-115">El puerto del servicio SMTP en el host.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-115">Port of the SMTP service in the host.</span></span>|  
|<span data-ttu-id="8e5a2-116">EnableSsl</span><span class="sxs-lookup"><span data-stu-id="8e5a2-116">EnableSsl</span></span>|<span data-ttu-id="8e5a2-117">bool</span><span class="sxs-lookup"><span data-stu-id="8e5a2-117">bool</span></span>|<span data-ttu-id="8e5a2-118">Especifica si el objeto <xref:System.Net.Mail.SmtpClient> utiliza SSL (Secure Sockets Layer) para cifrar la conexión.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-118">Specifies whether the <xref:System.Net.Mail.SmtpClient> uses Secure Sockets Layer (SSL) to encrypt the connection.</span></span>|  
|<span data-ttu-id="8e5a2-119">UserName</span><span class="sxs-lookup"><span data-stu-id="8e5a2-119">UserName</span></span>|<span data-ttu-id="8e5a2-120">String</span><span class="sxs-lookup"><span data-stu-id="8e5a2-120">String</span></span>|<span data-ttu-id="8e5a2-121">Nombre de usuario para preparar las credenciales para autenticar la propiedad <xref:System.Net.Mail.SmtpClient.Credentials%2A> del remitente.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-121">Username to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="8e5a2-122">Contraseña</span><span class="sxs-lookup"><span data-stu-id="8e5a2-122">Password</span></span>|<span data-ttu-id="8e5a2-123">String</span><span class="sxs-lookup"><span data-stu-id="8e5a2-123">String</span></span>|<span data-ttu-id="8e5a2-124">Contraseña para preparar las credenciales para autenticar la propiedad <xref:System.Net.Mail.SmtpClient.Credentials%2A> del remitente.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-124">Password to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="8e5a2-125">Contenido</span><span class="sxs-lookup"><span data-stu-id="8e5a2-125">Subject</span></span>|<span data-ttu-id="8e5a2-126"><xref:System.Activities.InArgument%601>\<cadena ></span><span class="sxs-lookup"><span data-stu-id="8e5a2-126"><xref:System.Activities.InArgument%601>\<string></span></span>|<span data-ttu-id="8e5a2-127">Asunto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-127">Subject of the message.</span></span>|  
|<span data-ttu-id="8e5a2-128">Cuerpo</span><span class="sxs-lookup"><span data-stu-id="8e5a2-128">Body</span></span>|<span data-ttu-id="8e5a2-129"><xref:System.Activities.InArgument%601>\<cadena ></span><span class="sxs-lookup"><span data-stu-id="8e5a2-129"><xref:System.Activities.InArgument%601>\<string></span></span>|<span data-ttu-id="8e5a2-130">Cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-130">Body of the message.</span></span>|  
|<span data-ttu-id="8e5a2-131">Datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="8e5a2-131">Attachments</span></span>|<span data-ttu-id="8e5a2-132"><xref:System.Activities.InArgument%601>\<cadena ></span><span class="sxs-lookup"><span data-stu-id="8e5a2-132"><xref:System.Activities.InArgument%601>\<string></span></span>|<span data-ttu-id="8e5a2-133">Colección de datos adjuntos que se usa para almacenar los datos adjuntados a este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-133">Attachment collection used to store data attached to this email message.</span></span>|  
|<span data-ttu-id="8e5a2-134">De</span><span class="sxs-lookup"><span data-stu-id="8e5a2-134">From</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="8e5a2-135">Desde la dirección de este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-135">From address for this email message.</span></span>|  
|<span data-ttu-id="8e5a2-136">En</span><span class="sxs-lookup"><span data-stu-id="8e5a2-136">To</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="8e5a2-137">Colección de direcciones que contiene a los destinatarios de este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-137">Address collection that contains the recipients of this email message.</span></span>|  
|<span data-ttu-id="8e5a2-138">CC</span><span class="sxs-lookup"><span data-stu-id="8e5a2-138">CC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="8e5a2-139">Colección de direcciones que contiene a los destinatarios de copia carbón (CC) de este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-139">Address collection that contains the carbon copy (CC) recipients for this email message.</span></span>|  
|<span data-ttu-id="8e5a2-140">BCC</span><span class="sxs-lookup"><span data-stu-id="8e5a2-140">BCC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="8e5a2-141">Colección de direcciones que contiene a los destinatarios de copia carbón oculta (CCO) de este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-141">Address collection that contains the blind carbon copy (BCC) recipients for this email message.</span></span>|  
|<span data-ttu-id="8e5a2-142">tokens</span><span class="sxs-lookup"><span data-stu-id="8e5a2-142">Tokens</span></span>|<span data-ttu-id="8e5a2-143"><xref:System.Activities.InArgument%601>< IDictionary\<cadena, cadena >></span><span class="sxs-lookup"><span data-stu-id="8e5a2-143"><xref:System.Activities.InArgument%601><IDictionary\<string, string>></span></span>|<span data-ttu-id="8e5a2-144">Tokens para reemplazar en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-144">Tokens to replace in the body.</span></span> <span data-ttu-id="8e5a2-145">Esta característica les permite a los usuarios especificar algunos valores del cuerpo que pueden ser reemplazados después por los tokens que proporcionó utilizando esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-145">This feature allows users to specify some values in the body than can be replaced later by the tokens provided using this property.</span></span>|  
|<span data-ttu-id="8e5a2-146">BodyTemplateFilePath</span><span class="sxs-lookup"><span data-stu-id="8e5a2-146">BodyTemplateFilePath</span></span>|<span data-ttu-id="8e5a2-147">String</span><span class="sxs-lookup"><span data-stu-id="8e5a2-147">String</span></span>|<span data-ttu-id="8e5a2-148">Ruta de acceso de una plantilla para el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-148">Path of a template for the body.</span></span> <span data-ttu-id="8e5a2-149">La actividad `SendMail` copia el contenido de este archivo en su propiedad de cuerpo.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-149">The `SendMail` activity copies the contents of this file to its body property.</span></span><br /><br /> <span data-ttu-id="8e5a2-150">La plantilla puede contener tokens que son reemplazados por el contenido de la propiedad de tokens.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-150">The template can contain tokens that are replaced by the contents of the tokens property.</span></span>|  
|<span data-ttu-id="8e5a2-151">TestMailTo</span><span class="sxs-lookup"><span data-stu-id="8e5a2-151">TestMailTo</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="8e5a2-152">Cuando se establece esta propiedad, todos los correos electrónicos se envían a la dirección especificada en él.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-152">When this property is set, all emails are sent to the address specified in it.</span></span><br /><br /> <span data-ttu-id="8e5a2-153">Se pretende que esta propiedad sea utilizada al probar los flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-153">This property is intended to be used when testing workflows.</span></span> <span data-ttu-id="8e5a2-154">Por ejemplo, cuando desee asegurarse de que todos los correos electrónicos se envían sin enviarlos a los destinatarios reales.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-154">For example, when you want to make sure that all emails are sent without sending them to the actual recipients.</span></span>|  
|<span data-ttu-id="8e5a2-155">TestDropPath</span><span class="sxs-lookup"><span data-stu-id="8e5a2-155">TestDropPath</span></span>|<span data-ttu-id="8e5a2-156">String</span><span class="sxs-lookup"><span data-stu-id="8e5a2-156">String</span></span>|<span data-ttu-id="8e5a2-157">Cuando se establece esta propiedad, todos los correos electrónicos se guardan también en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-157">When this property is set, all emails are also saved in the specified file.</span></span><br /><br /> <span data-ttu-id="8e5a2-158">Esta propiedad está pensada para utilizarse cuando se está probando o depurar flujos de trabajo, para asegurarse de que el formato y el contenido de los correos electrónicos salientes es adecuado.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-158">This property is intended to be used when you are testing or debugging workflows, to make sure that the format and contents of the outgoing emails is appropriate.</span></span>|  
  
## <a name="solution-contents"></a><span data-ttu-id="8e5a2-159">Contenido de la solución</span><span class="sxs-lookup"><span data-stu-id="8e5a2-159">Solution Contents</span></span>  
 <span data-ttu-id="8e5a2-160">La solución contiene dos proyectos.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-160">The solution contains two projects.</span></span>  
  
|<span data-ttu-id="8e5a2-161">Project</span><span class="sxs-lookup"><span data-stu-id="8e5a2-161">Project</span></span>|<span data-ttu-id="8e5a2-162">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e5a2-162">Description</span></span>|<span data-ttu-id="8e5a2-163">Archivos importantes</span><span class="sxs-lookup"><span data-stu-id="8e5a2-163">Important Files</span></span>|  
|-------------|-----------------|---------------------|  
|<span data-ttu-id="8e5a2-164">SendMail</span><span class="sxs-lookup"><span data-stu-id="8e5a2-164">SendMail</span></span>|<span data-ttu-id="8e5a2-165">La actividad SendMail</span><span class="sxs-lookup"><span data-stu-id="8e5a2-165">The SendMail activity</span></span>|<span data-ttu-id="8e5a2-166">1.  SendMail.cs: implementación para la actividad principal</span><span class="sxs-lookup"><span data-stu-id="8e5a2-166">1.  SendMail.cs: implementation for the main activity</span></span><br /><span data-ttu-id="8e5a2-167">2.  SendMailDesigner.xaml y SendMailDesigner.xaml.cs: diseñador para la actividad SendMail</span><span class="sxs-lookup"><span data-stu-id="8e5a2-167">2.  SendMailDesigner.xaml and SendMailDesigner.xaml.cs: designer for the SendMail activity</span></span><br /><span data-ttu-id="8e5a2-168">3.  MailTemplateBody.htm: la plantilla para el correo electrónico que se va a enviar.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-168">3.  MailTemplateBody.htm: template for the email to be sent out.</span></span>|  
|<span data-ttu-id="8e5a2-169">SendMailTestClient</span><span class="sxs-lookup"><span data-stu-id="8e5a2-169">SendMailTestClient</span></span>|<span data-ttu-id="8e5a2-170">Cliente para probar la actividad SendMail.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-170">Client to test the SendMail activity.</span></span>  <span data-ttu-id="8e5a2-171">Este proyecto muestra dos maneras de invocar la actividad SendMail: mediante declaración y mediante programación.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-171">This project demonstrates two ways of invoking the SendMail activity: declaratively, and programmatically.</span></span>|<span data-ttu-id="8e5a2-172">1.  Sequence1.xaml: flujo de trabajo que invoca la actividad SendMail.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-172">1.  Sequence1.xaml: workflow that invokes the SendMail activity.</span></span><br /><span data-ttu-id="8e5a2-173">2.  Program.cs: invoca Sequence1 y también crea un flujo de trabajo mediante programación que utiliza SendMail.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-173">2.  Program.cs: invokes Sequence1 and also creates a workflow programmatically that uses SendMail.</span></span>|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a><span data-ttu-id="8e5a2-174">Nueva configuración de la actividad SendMail</span><span class="sxs-lookup"><span data-stu-id="8e5a2-174">Further configuration of the SendMail activity</span></span>  
 <span data-ttu-id="8e5a2-175">Aunque no se muestra en el ejemplo, los usuarios pueden realizar una configuración adicional de la actividad SendMail.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-175">Although not shown in the sample, users can perform addition configuration of the SendMail activity.</span></span> <span data-ttu-id="8e5a2-176">Las tres secciones siguientes muestran cómo se hace esto.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-176">The next three sections demonstrate how this is done.</span></span>  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a><span data-ttu-id="8e5a2-177">Enviar un correo electrónico mediante los tokens especificados en el cuerpo</span><span class="sxs-lookup"><span data-stu-id="8e5a2-177">Sending an email using tokens specified in the body</span></span>  
 <span data-ttu-id="8e5a2-178">Este fragmento de código muestra cómo puede enviar el correo electrónico con tokens en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-178">This code snippet demonstrates how you can send email with tokens in the body.</span></span> <span data-ttu-id="8e5a2-179">Observe que los tokens se proporcionan en la propiedad del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-179">Notice how the tokens are provided in the body property.</span></span> <span data-ttu-id="8e5a2-180">Los valores para esos tokens se proporcionan a la propiedad de tokens.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-180">Values for those tokens are provided to the tokens property.</span></span>  
  
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
  
### <a name="sending-an-email-using-a-template"></a><span data-ttu-id="8e5a2-181">Enviar un correo electrónico mediante una plantilla</span><span class="sxs-lookup"><span data-stu-id="8e5a2-181">Sending an email using a template</span></span>  
 <span data-ttu-id="8e5a2-182">Este fragmento de código muestra cómo enviar un correo electrónico utilizando tokens de la plantilla en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-182">This snippet shows how to send an email using a template tokens in the body.</span></span> <span data-ttu-id="8e5a2-183">Observe que al establecer la propiedad `BodyTemplateFilePath` no necesitamos proporcionar el valor de la propiedad Body (el contenido del archivo de plantilla se copiará en el cuerpo).</span><span class="sxs-lookup"><span data-stu-id="8e5a2-183">Notice that when setting the `BodyTemplateFilePath` property we don’t need to provide the value for Body property (the contents of the template file will be copied to the body).</span></span>  
  
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
  
### <a name="sending-mails-in-testing-mode"></a><span data-ttu-id="8e5a2-184">Enviar correo en modo de prueba</span><span class="sxs-lookup"><span data-stu-id="8e5a2-184">Sending Mails in Testing Mode</span></span>  
 <span data-ttu-id="8e5a2-185">Este fragmento de código muestra cómo establecer las dos propiedades de pruebas: estableciendo `TestMailTo` a todos los mensajes se enviarán a john.doe@contoso.con (independientemente de los valores de para, Cc, CCO).</span><span class="sxs-lookup"><span data-stu-id="8e5a2-185">This code snippet shows how to set the two testing properties: by setting `TestMailTo` to all messages will be sent to john.doe@contoso.con (without regard of the values of To, Cc, Bcc).</span></span> <span data-ttu-id="8e5a2-186">Estableciendo que todos los correos electrónicos de salida a TestDropPath se registrarán también en la ruta de acceso proporcionada.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-186">By setting TestDropPath all outgoing emails will be also recorded in the provided path.</span></span> <span data-ttu-id="8e5a2-187">Estas propiedades se pueden establecer independientemente (no están relacionadas).</span><span class="sxs-lookup"><span data-stu-id="8e5a2-187">These properties can be set independently (they are not related).</span></span>  
  
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
  
## <a name="set-up-instructions"></a><span data-ttu-id="8e5a2-188">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="8e5a2-188">Set-Up Instructions</span></span>  
 <span data-ttu-id="8e5a2-189">En este ejemplo se requiere acceso a un servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-189">Access to a SMTP server is required for this sample.</span></span>  
  
 <span data-ttu-id="8e5a2-190">Para obtener más información acerca de cómo configurar un servidor SMTP, vea los vínculos siguientes.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-190">For more information about setting up a SMTP server, see the following links.</span></span>  
  
-   [<span data-ttu-id="8e5a2-191">Microsoft Technet</span><span class="sxs-lookup"><span data-stu-id="8e5a2-191">Microsoft Technet</span></span>](https://go.microsoft.com/fwlink/?LinkId=166060)  
  
-   [<span data-ttu-id="8e5a2-192">Configurar el servicio SMTP (IIS 6.0)</span><span class="sxs-lookup"><span data-stu-id="8e5a2-192">Configuring the SMTP Service (IIS 6.0)</span></span>](https://go.microsoft.com/fwlink/?LinkId=150456)  
  
-   [<span data-ttu-id="8e5a2-193">IIS 7.0: Configurar el correo electrónico SMTP</span><span class="sxs-lookup"><span data-stu-id="8e5a2-193">IIS 7.0: Configure SMTP E-Mail</span></span>](https://go.microsoft.com/fwlink/?LinkId=150457)  
  
-   [<span data-ttu-id="8e5a2-194">Cómo instalar el servicio SMTP</span><span class="sxs-lookup"><span data-stu-id="8e5a2-194">How to Install the SMTP Service</span></span>](https://go.microsoft.com/fwlink/?LinkId=150458)  
  
 <span data-ttu-id="8e5a2-195">Hay disponibles para descarga emuladores de SMTP proporcionados por terceros.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-195">SMTP emulators provided by third parties are available for download.</span></span>  
  
##### <a name="to-run-this-sample"></a><span data-ttu-id="8e5a2-196">Para ejecutar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="8e5a2-196">To run this sample</span></span>  
  
1.  <span data-ttu-id="8e5a2-197">Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución SendMail.sln de la solución.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-197">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the SendMail.sln solution file.</span></span>  
  
2.  <span data-ttu-id="8e5a2-198">Asegúrese de que tiene acceso a un servidor SMTP válido.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-198">Ensure that you have access to a valid SMTP server.</span></span> <span data-ttu-id="8e5a2-199">Vea las instrucciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-199">See the set-up instructions.</span></span>  
  
3.  <span data-ttu-id="8e5a2-200">Configure el programa con la dirección del servidor y desde y a las direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-200">Configure the program with your server address, and From and To email addresses.</span></span>  
  
     <span data-ttu-id="8e5a2-201">Para ejecutar correctamente este ejemplo, debe configurar el valor de desde y hacia las direcciones de correo electrónico y la dirección del servidor SMTP en Program.cs y en Sequence.xaml.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-201">To correctly run this sample, you may need to configure the value of From and To email addresses and the address of the SMTP server in  Program.cs and in Sequence.xaml.</span></span> <span data-ttu-id="8e5a2-202">Necesitará cambiar la dirección en ambas ubicaciones, dado que el programa envía el correo de dos maneras diferentes</span><span class="sxs-lookup"><span data-stu-id="8e5a2-202">You will need to change the address in both locations since the program sends mail in two different ways</span></span>  
  
4.  <span data-ttu-id="8e5a2-203">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-203">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5.  <span data-ttu-id="8e5a2-204">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-204">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8e5a2-205">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-205">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8e5a2-206">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-206">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8e5a2-207">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-207">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8e5a2-208">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-208">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`