---
title: Actividad personalizada SendMail
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bffca162bfa7bf5a4d2b1bf23566f2b039391f4c
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="sendmail-custom-activity"></a><span data-ttu-id="5da94-102">Actividad personalizada SendMail</span><span class="sxs-lookup"><span data-stu-id="5da94-102">SendMail Custom Activity</span></span>
<span data-ttu-id="5da94-103">En este ejemplo se muestra cómo crear una actividad personalizada que deriva de <xref:System.Activities.AsyncCodeActivity> para enviar correo utilizando SMTP para el uso dentro de una aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5da94-103">This sample demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span> <span data-ttu-id="5da94-104">La actividad personalizada utiliza las capacidades de <xref:System.Net.Mail.SmtpClient> para enviar el correo electrónico de forma asincrónica y enviar el correo con autenticación.</span><span class="sxs-lookup"><span data-stu-id="5da94-104">The custom activity uses the capabilities of <xref:System.Net.Mail.SmtpClient> to send e-mail asynchronously and to send mail with authentication.</span></span> <span data-ttu-id="5da94-105">También proporciona algunas características de usuario final como el modo de prueba, reemplazo del token, plantillas de archivo y ruta de acceso para dejar la prueba.</span><span class="sxs-lookup"><span data-stu-id="5da94-105">It also provides some end-user features like test mode, token replacement, file templates, and test drop path.</span></span>  
  
 <span data-ttu-id="5da94-106">En la siguiente tabla se detallan los argumentos de la actividad `SendMail`.</span><span class="sxs-lookup"><span data-stu-id="5da94-106">The following table details the arguments for the `SendMail` activity.</span></span>  
  
|<span data-ttu-id="5da94-107">Name</span><span class="sxs-lookup"><span data-stu-id="5da94-107">Name</span></span>|<span data-ttu-id="5da94-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="5da94-108">Type</span></span>|<span data-ttu-id="5da94-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="5da94-109">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="5da94-110">Host</span><span class="sxs-lookup"><span data-stu-id="5da94-110">Host</span></span>|<span data-ttu-id="5da94-111">String</span><span class="sxs-lookup"><span data-stu-id="5da94-111">String</span></span>|<span data-ttu-id="5da94-112">Dirección del host del servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="5da94-112">Address of the SMTP server host.</span></span>|  
|<span data-ttu-id="5da94-113">Puerto</span><span class="sxs-lookup"><span data-stu-id="5da94-113">Port</span></span>|<span data-ttu-id="5da94-114">String</span><span class="sxs-lookup"><span data-stu-id="5da94-114">String</span></span>|<span data-ttu-id="5da94-115">El puerto del servicio SMTP en el host.</span><span class="sxs-lookup"><span data-stu-id="5da94-115">Port of the SMTP service in the host.</span></span>|  
|<span data-ttu-id="5da94-116">EnableSsl</span><span class="sxs-lookup"><span data-stu-id="5da94-116">EnableSsl</span></span>|<span data-ttu-id="5da94-117">bool</span><span class="sxs-lookup"><span data-stu-id="5da94-117">bool</span></span>|<span data-ttu-id="5da94-118">Especifica si el objeto <xref:System.Net.Mail.SmtpClient> utiliza SSL (Secure Sockets Layer) para cifrar la conexión.</span><span class="sxs-lookup"><span data-stu-id="5da94-118">Specifies whether the <xref:System.Net.Mail.SmtpClient> uses Secure Sockets Layer (SSL) to encrypt the connection.</span></span>|  
|<span data-ttu-id="5da94-119">UserName</span><span class="sxs-lookup"><span data-stu-id="5da94-119">UserName</span></span>|<span data-ttu-id="5da94-120">String</span><span class="sxs-lookup"><span data-stu-id="5da94-120">String</span></span>|<span data-ttu-id="5da94-121">Nombre de usuario para preparar las credenciales para autenticar la propiedad <xref:System.Net.Mail.SmtpClient.Credentials%2A> del remitente.</span><span class="sxs-lookup"><span data-stu-id="5da94-121">Username to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="5da94-122">Contraseña</span><span class="sxs-lookup"><span data-stu-id="5da94-122">Password</span></span>|<span data-ttu-id="5da94-123">String</span><span class="sxs-lookup"><span data-stu-id="5da94-123">String</span></span>|<span data-ttu-id="5da94-124">Contraseña para preparar las credenciales para autenticar la propiedad <xref:System.Net.Mail.SmtpClient.Credentials%2A> del remitente.</span><span class="sxs-lookup"><span data-stu-id="5da94-124">Password to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="5da94-125">Contenido</span><span class="sxs-lookup"><span data-stu-id="5da94-125">Subject</span></span>|<span data-ttu-id="5da94-126"><xref:System.Activities.InArgument%601>\<cadena ></span><span class="sxs-lookup"><span data-stu-id="5da94-126"><xref:System.Activities.InArgument%601>\<string></span></span>|<span data-ttu-id="5da94-127">Asunto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5da94-127">Subject of the message.</span></span>|  
|<span data-ttu-id="5da94-128">Body</span><span class="sxs-lookup"><span data-stu-id="5da94-128">Body</span></span>|<span data-ttu-id="5da94-129"><xref:System.Activities.InArgument%601>\<cadena ></span><span class="sxs-lookup"><span data-stu-id="5da94-129"><xref:System.Activities.InArgument%601>\<string></span></span>|<span data-ttu-id="5da94-130">Cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5da94-130">Body of the message.</span></span>|  
|<span data-ttu-id="5da94-131">Datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="5da94-131">Attachments</span></span>|<span data-ttu-id="5da94-132"><xref:System.Activities.InArgument%601>\<cadena ></span><span class="sxs-lookup"><span data-stu-id="5da94-132"><xref:System.Activities.InArgument%601>\<string></span></span>|<span data-ttu-id="5da94-133">Colección de datos adjuntos que se utiliza para almacenar los datos adjuntos a este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5da94-133">Attachment collection used to store data attached to this e-mail message.</span></span>|  
|<span data-ttu-id="5da94-134">De</span><span class="sxs-lookup"><span data-stu-id="5da94-134">From</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="5da94-135">Dirección del remitente de este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5da94-135">From address for this e-mail message.</span></span>|  
|<span data-ttu-id="5da94-136">En</span><span class="sxs-lookup"><span data-stu-id="5da94-136">To</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="5da94-137">Colección de direcciones que contiene los destinatarios de este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5da94-137">Address collection that contains the recipients of this e-mail message.</span></span>|  
|<span data-ttu-id="5da94-138">CC</span><span class="sxs-lookup"><span data-stu-id="5da94-138">CC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="5da94-139">Colección de direcciones que contiene los destinatarios para recibir copia (CC) de este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5da94-139">Address collection that contains the carbon copy (CC) recipients for this e-mail message.</span></span>|  
|<span data-ttu-id="5da94-140">BCC</span><span class="sxs-lookup"><span data-stu-id="5da94-140">BCC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="5da94-141">Colección de direcciones que contiene los destinatarios ocultos de copia (CCO) de este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5da94-141">Address collection that contains the blind carbon copy (BCC) recipients for this e-mail message.</span></span>|  
|<span data-ttu-id="5da94-142">tokens</span><span class="sxs-lookup"><span data-stu-id="5da94-142">Tokens</span></span>|<span data-ttu-id="5da94-143"><xref:System.Activities.InArgument%601>< IDictionary\<cadena, cadena >></span><span class="sxs-lookup"><span data-stu-id="5da94-143"><xref:System.Activities.InArgument%601><IDictionary\<string, string>></span></span>|<span data-ttu-id="5da94-144">Tokens para reemplazar en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="5da94-144">Tokens to replace in the body.</span></span> <span data-ttu-id="5da94-145">Esta característica les permite a los usuarios especificar algunos valores del cuerpo que pueden ser reemplazados después por los tokens que proporcionó utilizando esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="5da94-145">This feature allows users to specify some values in the body than can be replaced later by the tokens provided using this property.</span></span>|  
|<span data-ttu-id="5da94-146">BodyTemplateFilePath</span><span class="sxs-lookup"><span data-stu-id="5da94-146">BodyTemplateFilePath</span></span>|<span data-ttu-id="5da94-147">String</span><span class="sxs-lookup"><span data-stu-id="5da94-147">String</span></span>|<span data-ttu-id="5da94-148">Ruta de acceso de una plantilla para el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="5da94-148">Path of a template for the body.</span></span> <span data-ttu-id="5da94-149">La actividad `SendMail` copia el contenido de este archivo en su propiedad de cuerpo.</span><span class="sxs-lookup"><span data-stu-id="5da94-149">The `SendMail` activity copies the contents of this file to its body property.</span></span><br /><br /> <span data-ttu-id="5da94-150">La plantilla puede contener tokens que son reemplazados por el contenido de la propiedad de tokens.</span><span class="sxs-lookup"><span data-stu-id="5da94-150">The template can contain tokens that are replaced by the contents of the tokens property.</span></span>|  
|<span data-ttu-id="5da94-151">TestMailTo</span><span class="sxs-lookup"><span data-stu-id="5da94-151">TestMailTo</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="5da94-152">Cuando se establece esta propiedad, todos los correos electrónicos se envían a la dirección especificada en él.</span><span class="sxs-lookup"><span data-stu-id="5da94-152">When this property is set, all e-mails are sent to the address specified in it.</span></span><br /><br /> <span data-ttu-id="5da94-153">Se pretende que esta propiedad sea utilizada al probar los flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5da94-153">This property is intended to be used when testing workflows.</span></span> <span data-ttu-id="5da94-154">Por ejemplo, cuando desea asegurarse de que todos los correo electrónicos se envíen sin enviarlos a los destinatarios reales.</span><span class="sxs-lookup"><span data-stu-id="5da94-154">For example, when you want to make sure that all e-mails are sent without sending them to the actual recipients.</span></span>|  
|<span data-ttu-id="5da94-155">TestDropPath</span><span class="sxs-lookup"><span data-stu-id="5da94-155">TestDropPath</span></span>|<span data-ttu-id="5da94-156">String</span><span class="sxs-lookup"><span data-stu-id="5da94-156">String</span></span>|<span data-ttu-id="5da94-157">Cuando se establece esta propiedad, todos los correos electrónicos se guardan también en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="5da94-157">When this property is set, all e-mails are also saved in the specified file.</span></span><br /><br /> <span data-ttu-id="5da94-158">Se pretende que esta propiedad sea utilizada cuando prueba o depura flujos de trabajo, para asegurarse de que el formato y contenido de los mensajes de correo electrónico salientes son adecuados.</span><span class="sxs-lookup"><span data-stu-id="5da94-158">This property is intended to be used when you are testing or debugging workflows, to make sure that the format and contents of the outgoing e-mails is appropriate.</span></span>|  
  
## <a name="solution-contents"></a><span data-ttu-id="5da94-159">Contenido de la solución</span><span class="sxs-lookup"><span data-stu-id="5da94-159">Solution Contents</span></span>  
 <span data-ttu-id="5da94-160">La solución contiene dos proyectos.</span><span class="sxs-lookup"><span data-stu-id="5da94-160">The solution contains two projects.</span></span>  
  
|<span data-ttu-id="5da94-161">Project</span><span class="sxs-lookup"><span data-stu-id="5da94-161">Project</span></span>|<span data-ttu-id="5da94-162">Descripción</span><span class="sxs-lookup"><span data-stu-id="5da94-162">Description</span></span>|<span data-ttu-id="5da94-163">Archivos importantes</span><span class="sxs-lookup"><span data-stu-id="5da94-163">Important Files</span></span>|  
|-------------|-----------------|---------------------|  
|<span data-ttu-id="5da94-164">SendMail</span><span class="sxs-lookup"><span data-stu-id="5da94-164">SendMail</span></span>|<span data-ttu-id="5da94-165">La actividad SendMail</span><span class="sxs-lookup"><span data-stu-id="5da94-165">The SendMail activity</span></span>|<span data-ttu-id="5da94-166">1.  SendMail.cs: implementación para la actividad principal</span><span class="sxs-lookup"><span data-stu-id="5da94-166">1.  SendMail.cs: implementation for the main activity</span></span><br /><span data-ttu-id="5da94-167">2.  SendMailDesigner.xaml y SendMailDesigner.xaml.cs: diseñador para la actividad SendMail</span><span class="sxs-lookup"><span data-stu-id="5da94-167">2.  SendMailDesigner.xaml and SendMailDesigner.xaml.cs: designer for the SendMail activity</span></span><br /><span data-ttu-id="5da94-168">3.  MailTemplateBody.htm: la plantilla para el correo electrónico que se va a enviar.</span><span class="sxs-lookup"><span data-stu-id="5da94-168">3.  MailTemplateBody.htm: template for the email to be sent out.</span></span>|  
|<span data-ttu-id="5da94-169">SendMailTestClient</span><span class="sxs-lookup"><span data-stu-id="5da94-169">SendMailTestClient</span></span>|<span data-ttu-id="5da94-170">Cliente para probar la actividad SendMail.</span><span class="sxs-lookup"><span data-stu-id="5da94-170">Client to test the SendMail activity.</span></span>  <span data-ttu-id="5da94-171">Este proyecto muestra dos maneras de invocar la actividad SendMail: mediante declaración y mediante programación.</span><span class="sxs-lookup"><span data-stu-id="5da94-171">This project demonstrates two ways of invoking the SendMail activity: declaratively, and programmatically.</span></span>|<span data-ttu-id="5da94-172">1.  Sequence1.xaml: flujo de trabajo que invoca la actividad SendMail.</span><span class="sxs-lookup"><span data-stu-id="5da94-172">1.  Sequence1.xaml: workflow that invokes the SendMail activity.</span></span><br /><span data-ttu-id="5da94-173">2.  Program.cs: invoca Sequence1 y también crea un flujo de trabajo mediante programación que utiliza SendMail.</span><span class="sxs-lookup"><span data-stu-id="5da94-173">2.  Program.cs: invokes Sequence1 and also creates a workflow programmatically that uses SendMail.</span></span>|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a><span data-ttu-id="5da94-174">Nueva configuración de la actividad SendMail</span><span class="sxs-lookup"><span data-stu-id="5da94-174">Further configuration of the SendMail activity</span></span>  
 <span data-ttu-id="5da94-175">Aunque no se muestra en el ejemplo, los usuarios pueden realizar una configuración adicional de la actividad SendMail.</span><span class="sxs-lookup"><span data-stu-id="5da94-175">Although not shown in the sample, users can perform addition configuration of the SendMail activity.</span></span> <span data-ttu-id="5da94-176">Las tres secciones siguientes muestran cómo se hace esto.</span><span class="sxs-lookup"><span data-stu-id="5da94-176">The next three sections demonstrate how this is done.</span></span>  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a><span data-ttu-id="5da94-177">Enviar un correo electrónico mediante los tokens especificados en el cuerpo</span><span class="sxs-lookup"><span data-stu-id="5da94-177">Sending an email using tokens specified in the body</span></span>  
 <span data-ttu-id="5da94-178">Este fragmento de código muestra cómo puede enviar el correo electrónico con tokens en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="5da94-178">This code snippet demonstrates how you can send email with tokens in the body.</span></span> <span data-ttu-id="5da94-179">Observe que los tokens se proporcionan en la propiedad del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="5da94-179">Notice how the tokens are provided in the body property.</span></span> <span data-ttu-id="5da94-180">Los valores para esos tokens se proporcionan a la propiedad de tokens.</span><span class="sxs-lookup"><span data-stu-id="5da94-180">Values for those tokens are provided to the tokens property.</span></span>  
  
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
  
### <a name="sending-an-email-using-a-template"></a><span data-ttu-id="5da94-181">Enviar un correo electrónico mediante una plantilla</span><span class="sxs-lookup"><span data-stu-id="5da94-181">Sending an email using a template</span></span>  
 <span data-ttu-id="5da94-182">Este fragmento de código muestra cómo enviar un correo electrónico utilizando tokens de la plantilla en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="5da94-182">This snippet shows how to send an email using a template tokens in the body.</span></span> <span data-ttu-id="5da94-183">Observe que al establecer la propiedad `BodyTemplateFilePath` no necesitamos proporcionar el valor de la propiedad Body (el contenido del archivo de plantilla se copiará en el cuerpo).</span><span class="sxs-lookup"><span data-stu-id="5da94-183">Notice that when setting the `BodyTemplateFilePath` property we don’t need to provide the value for Body property (the contents of the template file will be copied to the body).</span></span>  
  
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
  
### <a name="sending-mails-in-testing-mode"></a><span data-ttu-id="5da94-184">Enviar correo en modo de prueba</span><span class="sxs-lookup"><span data-stu-id="5da94-184">Sending Mails in Testing Mode</span></span>  
 <span data-ttu-id="5da94-185">Este fragmento de código muestra cómo establecer las dos propiedades de prueba: estableciendo `TestMailTo` a todos los mensajes se enviarán a john.doe@contoso.con (sin tener en cuenta de los valores de para, Cc, CCO).</span><span class="sxs-lookup"><span data-stu-id="5da94-185">This code snippet shows how to set the two testing properties: by setting `TestMailTo` to all messages will be sent to john.doe@contoso.con (without regard of the values of To, Cc, Bcc).</span></span> <span data-ttu-id="5da94-186">Estableciendo que todos los correos electrónicos de salida a TestDropPath se registrarán también en la ruta de acceso proporcionada.</span><span class="sxs-lookup"><span data-stu-id="5da94-186">By setting TestDropPath all outgoing emails will be also recorded in the provided path.</span></span> <span data-ttu-id="5da94-187">Estas propiedades se pueden establecer independientemente (no están relacionadas).</span><span class="sxs-lookup"><span data-stu-id="5da94-187">These properties can be set independently (they are not related).</span></span>  
  
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
  
## <a name="set-up-instructions"></a><span data-ttu-id="5da94-188">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="5da94-188">Set-Up Instructions</span></span>  
 <span data-ttu-id="5da94-189">En este ejemplo se requiere acceso a un servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="5da94-189">Access to a SMTP server is required for this sample.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="5da94-190">configuración de un servidor SMTP, consulte los vínculos siguientes.</span><span class="sxs-lookup"><span data-stu-id="5da94-190"> setting up a SMTP server, see the following links.</span></span>  
  
-   [<span data-ttu-id="5da94-191">Microsoft Technet</span><span class="sxs-lookup"><span data-stu-id="5da94-191">Microsoft Technet</span></span>](http://go.microsoft.com/fwlink/?LinkId=166060)  
  
-   [<span data-ttu-id="5da94-192">Configurar el servicio SMTP (IIS 6.0)</span><span class="sxs-lookup"><span data-stu-id="5da94-192">Configuring the SMTP Service (IIS 6.0)</span></span>](http://go.microsoft.com/fwlink/?LinkId=150456)  
  
-   [<span data-ttu-id="5da94-193">IIS 7.0: Configurar el correo electrónico SMTP</span><span class="sxs-lookup"><span data-stu-id="5da94-193">IIS 7.0: Configure SMTP E-Mail</span></span>](http://go.microsoft.com/fwlink/?LinkId=150457)  
  
-   [<span data-ttu-id="5da94-194">Cómo instalar el servicio SMTP</span><span class="sxs-lookup"><span data-stu-id="5da94-194">How to Install the SMTP Service</span></span>](http://go.microsoft.com/fwlink/?LinkId=150458)  
  
 <span data-ttu-id="5da94-195">Hay disponibles para descarga emuladores de SMTP proporcionados por terceros.</span><span class="sxs-lookup"><span data-stu-id="5da94-195">SMTP emulators provided by third parties are available for download.</span></span>  
  
##### <a name="to-run-this-sample"></a><span data-ttu-id="5da94-196">Para ejecutar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="5da94-196">To run this sample</span></span>  
  
1.  <span data-ttu-id="5da94-197">Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución SendMail.sln de la solución.</span><span class="sxs-lookup"><span data-stu-id="5da94-197">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the SendMail.sln solution file.</span></span>  
  
2.  <span data-ttu-id="5da94-198">Asegúrese de que tiene acceso a un servidor SMTP válido.</span><span class="sxs-lookup"><span data-stu-id="5da94-198">Ensure that you have access to a valid SMTP server.</span></span> <span data-ttu-id="5da94-199">Vea las instrucciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="5da94-199">See the set-up instructions.</span></span>  
  
3.  <span data-ttu-id="5da94-200">Configure el programa con su dirección de servidor y las direcciones de correo electrónico From y To.</span><span class="sxs-lookup"><span data-stu-id="5da94-200">Configure the program with your server address, and From and To e-mail addresses.</span></span>  
  
     <span data-ttu-id="5da94-201">Para ejecutar este ejemplo correctamente, puede necesitar configurar el valor de las direcciones de correo electrónico From y To, y la dirección del servidor SMTP, en Program.cs y en Sequence.xaml.</span><span class="sxs-lookup"><span data-stu-id="5da94-201">To correctly run this sample, you may need to configure the value of From and To e-mail addresses and the address of the SMTP server in  Program.cs and in Sequence.xaml.</span></span> <span data-ttu-id="5da94-202">Necesitará cambiar la dirección en ambas ubicaciones, dado que el programa envía el correo de dos maneras diferentes</span><span class="sxs-lookup"><span data-stu-id="5da94-202">You will need to change the address in both locations since the program sends mail in two different ways</span></span>  
  
4.  <span data-ttu-id="5da94-203">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="5da94-203">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5.  <span data-ttu-id="5da94-204">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="5da94-204">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5da94-205">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="5da94-205">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5da94-206">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="5da94-206">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5da94-207">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5da94-207">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5da94-208">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="5da94-208">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`