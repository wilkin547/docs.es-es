---
title: Actividad personalizada SendMail
ms.date: 03/30/2017
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
ms.openlocfilehash: b1e2d58a09362569d4d408f6e1c9e589aa6bda76
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715580"
---
# <a name="sendmail-custom-activity"></a><span data-ttu-id="91085-102">Actividad personalizada SendMail</span><span class="sxs-lookup"><span data-stu-id="91085-102">SendMail Custom Activity</span></span>
<span data-ttu-id="91085-103">En este ejemplo se muestra cómo crear una actividad personalizada que deriva de <xref:System.Activities.AsyncCodeActivity> para enviar correo utilizando SMTP para el uso dentro de una aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="91085-103">This sample demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span> <span data-ttu-id="91085-104">La actividad personalizada utiliza las capacidades de <xref:System.Net.Mail.SmtpClient> para enviar correo electrónico de forma asincrónica y enviar correo con autenticación.</span><span class="sxs-lookup"><span data-stu-id="91085-104">The custom activity uses the capabilities of <xref:System.Net.Mail.SmtpClient> to send email asynchronously and to send mail with authentication.</span></span> <span data-ttu-id="91085-105">También proporciona algunas características de usuario final como el modo de prueba, reemplazo del token, plantillas de archivo y ruta de colocación para dejar la prueba.</span><span class="sxs-lookup"><span data-stu-id="91085-105">It also provides some end-user features like test mode, token replacement, file templates, and test drop path.</span></span>  
  
 <span data-ttu-id="91085-106">En la siguiente tabla se detallan los argumentos de la actividad `SendMail`.</span><span class="sxs-lookup"><span data-stu-id="91085-106">The following table details the arguments for the `SendMail` activity.</span></span>  
  
|<span data-ttu-id="91085-107">Name</span><span class="sxs-lookup"><span data-stu-id="91085-107">Name</span></span>|<span data-ttu-id="91085-108">Tipo de</span><span class="sxs-lookup"><span data-stu-id="91085-108">Type</span></span>|<span data-ttu-id="91085-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="91085-109">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="91085-110">administrador de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="91085-110">Host</span></span>|<span data-ttu-id="91085-111">String</span><span class="sxs-lookup"><span data-stu-id="91085-111">String</span></span>|<span data-ttu-id="91085-112">Dirección del host del servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="91085-112">Address of the SMTP server host.</span></span>|  
|<span data-ttu-id="91085-113">Port</span><span class="sxs-lookup"><span data-stu-id="91085-113">Port</span></span>|<span data-ttu-id="91085-114">String</span><span class="sxs-lookup"><span data-stu-id="91085-114">String</span></span>|<span data-ttu-id="91085-115">El puerto del servicio SMTP en el host.</span><span class="sxs-lookup"><span data-stu-id="91085-115">Port of the SMTP service in the host.</span></span>|  
|<span data-ttu-id="91085-116">EnableSsl</span><span class="sxs-lookup"><span data-stu-id="91085-116">EnableSsl</span></span>|<span data-ttu-id="91085-117">bool</span><span class="sxs-lookup"><span data-stu-id="91085-117">bool</span></span>|<span data-ttu-id="91085-118">Especifica si el objeto <xref:System.Net.Mail.SmtpClient> utiliza SSL (Secure Sockets Layer) para cifrar la conexión.</span><span class="sxs-lookup"><span data-stu-id="91085-118">Specifies whether the <xref:System.Net.Mail.SmtpClient> uses Secure Sockets Layer (SSL) to encrypt the connection.</span></span>|  
|<span data-ttu-id="91085-119">UserName</span><span class="sxs-lookup"><span data-stu-id="91085-119">UserName</span></span>|<span data-ttu-id="91085-120">String</span><span class="sxs-lookup"><span data-stu-id="91085-120">String</span></span>|<span data-ttu-id="91085-121">Nombre de usuario para preparar las credenciales para autenticar la propiedad <xref:System.Net.Mail.SmtpClient.Credentials%2A> del remitente.</span><span class="sxs-lookup"><span data-stu-id="91085-121">Username to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="91085-122">Password</span><span class="sxs-lookup"><span data-stu-id="91085-122">Password</span></span>|<span data-ttu-id="91085-123">String</span><span class="sxs-lookup"><span data-stu-id="91085-123">String</span></span>|<span data-ttu-id="91085-124">Contraseña para preparar las credenciales para autenticar la propiedad <xref:System.Net.Mail.SmtpClient.Credentials%2A> del remitente.</span><span class="sxs-lookup"><span data-stu-id="91085-124">Password to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="91085-125">Subject</span><span class="sxs-lookup"><span data-stu-id="91085-125">Subject</span></span>|<span data-ttu-id="91085-126"><xref:System.Activities.InArgument%601>cadena de \<</span><span class="sxs-lookup"><span data-stu-id="91085-126"><xref:System.Activities.InArgument%601>\<string></span></span>|<span data-ttu-id="91085-127">Asunto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="91085-127">Subject of the message.</span></span>|  
|<span data-ttu-id="91085-128">Cuerpo</span><span class="sxs-lookup"><span data-stu-id="91085-128">Body</span></span>|<span data-ttu-id="91085-129"><xref:System.Activities.InArgument%601>cadena de \<</span><span class="sxs-lookup"><span data-stu-id="91085-129"><xref:System.Activities.InArgument%601>\<string></span></span>|<span data-ttu-id="91085-130">Cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="91085-130">Body of the message.</span></span>|  
|<span data-ttu-id="91085-131">Datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="91085-131">Attachments</span></span>|<span data-ttu-id="91085-132"><xref:System.Activities.InArgument%601>cadena de \<</span><span class="sxs-lookup"><span data-stu-id="91085-132"><xref:System.Activities.InArgument%601>\<string></span></span>|<span data-ttu-id="91085-133">Colección de datos adjuntos usada para almacenar datos adjuntos a este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="91085-133">Attachment collection used to store data attached to this email message.</span></span>|  
|<span data-ttu-id="91085-134">Desde un</span><span class="sxs-lookup"><span data-stu-id="91085-134">From</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="91085-135">Dirección de este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="91085-135">From address for this email message.</span></span>|  
|<span data-ttu-id="91085-136">En</span><span class="sxs-lookup"><span data-stu-id="91085-136">To</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="91085-137">Colección de direcciones que contiene los destinatarios de este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="91085-137">Address collection that contains the recipients of this email message.</span></span>|  
|<span data-ttu-id="91085-138">CC</span><span class="sxs-lookup"><span data-stu-id="91085-138">CC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="91085-139">Colección de direcciones que contiene los destinatarios de copia carbón (CC) de este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="91085-139">Address collection that contains the carbon copy (CC) recipients for this email message.</span></span>|  
|<span data-ttu-id="91085-140">BCC</span><span class="sxs-lookup"><span data-stu-id="91085-140">BCC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="91085-141">Colección de direcciones que contiene los destinatarios de copia carbón oculta (CCO) de este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="91085-141">Address collection that contains the blind carbon copy (BCC) recipients for this email message.</span></span>|  
|<span data-ttu-id="91085-142">tokens</span><span class="sxs-lookup"><span data-stu-id="91085-142">Tokens</span></span>|<span data-ttu-id="91085-143"><xref:System.Activities.InArgument%601>< IDictionary\<cadena, > de cadena ></span><span class="sxs-lookup"><span data-stu-id="91085-143"><xref:System.Activities.InArgument%601><IDictionary\<string, string>></span></span>|<span data-ttu-id="91085-144">Tokens para reemplazar en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="91085-144">Tokens to replace in the body.</span></span> <span data-ttu-id="91085-145">Esta característica les permite a los usuarios especificar algunos valores del cuerpo que pueden ser reemplazados después por los tokens que proporcionó utilizando esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="91085-145">This feature allows users to specify some values in the body than can be replaced later by the tokens provided using this property.</span></span>|  
|<span data-ttu-id="91085-146">BodyTemplateFilePath</span><span class="sxs-lookup"><span data-stu-id="91085-146">BodyTemplateFilePath</span></span>|<span data-ttu-id="91085-147">String</span><span class="sxs-lookup"><span data-stu-id="91085-147">String</span></span>|<span data-ttu-id="91085-148">Ruta de acceso de una plantilla para el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="91085-148">Path of a template for the body.</span></span> <span data-ttu-id="91085-149">La actividad `SendMail` copia el contenido de este archivo en su propiedad de cuerpo.</span><span class="sxs-lookup"><span data-stu-id="91085-149">The `SendMail` activity copies the contents of this file to its body property.</span></span><br /><br /> <span data-ttu-id="91085-150">La plantilla puede contener tokens que son reemplazados por el contenido de la propiedad de tokens.</span><span class="sxs-lookup"><span data-stu-id="91085-150">The template can contain tokens that are replaced by the contents of the tokens property.</span></span>|  
|<span data-ttu-id="91085-151">TestMailTo</span><span class="sxs-lookup"><span data-stu-id="91085-151">TestMailTo</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="91085-152">Cuando se establece esta propiedad, todos los correos electrónicos se envían a la dirección especificada en él.</span><span class="sxs-lookup"><span data-stu-id="91085-152">When this property is set, all emails are sent to the address specified in it.</span></span><br /><br /> <span data-ttu-id="91085-153">Se pretende que esta propiedad sea utilizada al probar los flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="91085-153">This property is intended to be used when testing workflows.</span></span> <span data-ttu-id="91085-154">Por ejemplo, si desea asegurarse de que todos los mensajes de correo electrónico se envían sin enviarlos a los destinatarios reales.</span><span class="sxs-lookup"><span data-stu-id="91085-154">For example, when you want to make sure that all emails are sent without sending them to the actual recipients.</span></span>|  
|<span data-ttu-id="91085-155">TestDropPath</span><span class="sxs-lookup"><span data-stu-id="91085-155">TestDropPath</span></span>|<span data-ttu-id="91085-156">String</span><span class="sxs-lookup"><span data-stu-id="91085-156">String</span></span>|<span data-ttu-id="91085-157">Cuando se establece esta propiedad, todos los correos electrónicos también se guardan en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="91085-157">When this property is set, all emails are also saved in the specified file.</span></span><br /><br /> <span data-ttu-id="91085-158">Esta propiedad está pensada para usarse al probar o Depurar flujos de trabajo, para asegurarse de que el formato y el contenido de los mensajes de correo electrónico salientes es adecuado.</span><span class="sxs-lookup"><span data-stu-id="91085-158">This property is intended to be used when you are testing or debugging workflows, to make sure that the format and contents of the outgoing emails is appropriate.</span></span>|  
  
## <a name="solution-contents"></a><span data-ttu-id="91085-159">Contenido de la solución</span><span class="sxs-lookup"><span data-stu-id="91085-159">Solution Contents</span></span>  
 <span data-ttu-id="91085-160">La solución contiene dos proyectos.</span><span class="sxs-lookup"><span data-stu-id="91085-160">The solution contains two projects.</span></span>  
  
|<span data-ttu-id="91085-161">Proyecto de</span><span class="sxs-lookup"><span data-stu-id="91085-161">Project</span></span>|<span data-ttu-id="91085-162">Descripción</span><span class="sxs-lookup"><span data-stu-id="91085-162">Description</span></span>|<span data-ttu-id="91085-163">Archivos importantes</span><span class="sxs-lookup"><span data-stu-id="91085-163">Important Files</span></span>|  
|-------------|-----------------|---------------------|  
|<span data-ttu-id="91085-164">SendMail</span><span class="sxs-lookup"><span data-stu-id="91085-164">SendMail</span></span>|<span data-ttu-id="91085-165">La actividad SendMail</span><span class="sxs-lookup"><span data-stu-id="91085-165">The SendMail activity</span></span>|<span data-ttu-id="91085-166">1. SendMail.cs: implementación para la actividad principal</span><span class="sxs-lookup"><span data-stu-id="91085-166">1.  SendMail.cs: implementation for the main activity</span></span><br /><span data-ttu-id="91085-167">2. SendMailDesigner. XAML y SendMailDesigner.xaml.cs: diseñador para la actividad SendMail</span><span class="sxs-lookup"><span data-stu-id="91085-167">2.  SendMailDesigner.xaml and SendMailDesigner.xaml.cs: designer for the SendMail activity</span></span><br /><span data-ttu-id="91085-168">3. MailTemplateBody. htm: plantilla para el correo electrónico que se va a enviar.</span><span class="sxs-lookup"><span data-stu-id="91085-168">3.  MailTemplateBody.htm: template for the email to be sent out.</span></span>|  
|<span data-ttu-id="91085-169">SendMailTestClient</span><span class="sxs-lookup"><span data-stu-id="91085-169">SendMailTestClient</span></span>|<span data-ttu-id="91085-170">Cliente para probar la actividad SendMail.</span><span class="sxs-lookup"><span data-stu-id="91085-170">Client to test the SendMail activity.</span></span>  <span data-ttu-id="91085-171">Este proyecto muestra dos maneras de invocar la actividad SendMail: mediante declaración y mediante programación.</span><span class="sxs-lookup"><span data-stu-id="91085-171">This project demonstrates two ways of invoking the SendMail activity: declaratively, and programmatically.</span></span>|<span data-ttu-id="91085-172">1. Sequence1. XAML: flujo de trabajo que invoca la actividad SendMail.</span><span class="sxs-lookup"><span data-stu-id="91085-172">1.  Sequence1.xaml: workflow that invokes the SendMail activity.</span></span><br /><span data-ttu-id="91085-173">2. Program.cs: invoca Sequence1 y también crea un flujo de trabajo mediante programación que usa SendMail.</span><span class="sxs-lookup"><span data-stu-id="91085-173">2.  Program.cs: invokes Sequence1 and also creates a workflow programmatically that uses SendMail.</span></span>|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a><span data-ttu-id="91085-174">Nueva configuración de la actividad SendMail</span><span class="sxs-lookup"><span data-stu-id="91085-174">Further configuration of the SendMail activity</span></span>  
 <span data-ttu-id="91085-175">Aunque no se muestra en el ejemplo, los usuarios pueden realizar una configuración adicional de la actividad SendMail.</span><span class="sxs-lookup"><span data-stu-id="91085-175">Although not shown in the sample, users can perform addition configuration of the SendMail activity.</span></span> <span data-ttu-id="91085-176">Las tres secciones siguientes muestran cómo se hace esto.</span><span class="sxs-lookup"><span data-stu-id="91085-176">The next three sections demonstrate how this is done.</span></span>  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a><span data-ttu-id="91085-177">Enviar un correo electrónico mediante los tokens especificados en el cuerpo</span><span class="sxs-lookup"><span data-stu-id="91085-177">Sending an email using tokens specified in the body</span></span>  
 <span data-ttu-id="91085-178">Este fragmento de código muestra cómo puede enviar el correo electrónico con tokens en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="91085-178">This code snippet demonstrates how you can send email with tokens in the body.</span></span> <span data-ttu-id="91085-179">Observe que los tokens se proporcionan en la propiedad del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="91085-179">Notice how the tokens are provided in the body property.</span></span> <span data-ttu-id="91085-180">Los valores para esos tokens se proporcionan a la propiedad de tokens.</span><span class="sxs-lookup"><span data-stu-id="91085-180">Values for those tokens are provided to the tokens property.</span></span>  
  
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
  
### <a name="sending-an-email-using-a-template"></a><span data-ttu-id="91085-181">Enviar un correo electrónico mediante una plantilla</span><span class="sxs-lookup"><span data-stu-id="91085-181">Sending an email using a template</span></span>  
 <span data-ttu-id="91085-182">Este fragmento de código muestra cómo enviar un correo electrónico utilizando tokens de la plantilla en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="91085-182">This snippet shows how to send an email using a template tokens in the body.</span></span> <span data-ttu-id="91085-183">Observe que al establecer la propiedad `BodyTemplateFilePath` no necesitamos proporcionar el valor de la propiedad Body (el contenido del archivo de plantilla se copiará en el cuerpo).</span><span class="sxs-lookup"><span data-stu-id="91085-183">Notice that when setting the `BodyTemplateFilePath` property we don’t need to provide the value for Body property (the contents of the template file will be copied to the body).</span></span>  
  
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
  
### <a name="sending-mails-in-testing-mode"></a><span data-ttu-id="91085-184">Enviar correo en modo de prueba</span><span class="sxs-lookup"><span data-stu-id="91085-184">Sending Mails in Testing Mode</span></span>  
 <span data-ttu-id="91085-185">Este fragmento de código muestra cómo establecer las dos propiedades de prueba: al establecer `TestMailTo` en todos los mensajes se enviarán a `john.doe@contoso.con` (sin tener en cuenta los valores de para, CC, CCO).</span><span class="sxs-lookup"><span data-stu-id="91085-185">This code snippet shows how to set the two testing properties: by setting `TestMailTo` to all messages will be sent to `john.doe@contoso.con` (without regard of the values of To, Cc, Bcc).</span></span> <span data-ttu-id="91085-186">Estableciendo que todos los correos electrónicos de salida a TestDropPath se registrarán también en la ruta de acceso proporcionada.</span><span class="sxs-lookup"><span data-stu-id="91085-186">By setting TestDropPath all outgoing emails will be also recorded in the provided path.</span></span> <span data-ttu-id="91085-187">Estas propiedades se pueden establecer independientemente (no están relacionadas).</span><span class="sxs-lookup"><span data-stu-id="91085-187">These properties can be set independently (they are not related).</span></span>  
  
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
  
## <a name="set-up-instructions"></a><span data-ttu-id="91085-188">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="91085-188">Set-Up Instructions</span></span>  
 <span data-ttu-id="91085-189">En este ejemplo se requiere acceso a un servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="91085-189">Access to a SMTP server is required for this sample.</span></span>  
  
 <span data-ttu-id="91085-190">Para obtener más información acerca de cómo configurar un servidor SMTP, consulte los siguientes vínculos.</span><span class="sxs-lookup"><span data-stu-id="91085-190">For more information about setting up a SMTP server, see the following links.</span></span>  
  
- [<span data-ttu-id="91085-191">Microsoft TechNet</span><span class="sxs-lookup"><span data-stu-id="91085-191">Microsoft Technet</span></span>](https://go.microsoft.com/fwlink/?LinkId=166060)  
  
- [<span data-ttu-id="91085-192">Configurar el servicio SMTP (IIS 6,0)</span><span class="sxs-lookup"><span data-stu-id="91085-192">Configuring the SMTP Service (IIS 6.0)</span></span>](https://go.microsoft.com/fwlink/?LinkId=150456)  
  
- [<span data-ttu-id="91085-193">IIS 7,0: configurar el correo electrónico SMTP</span><span class="sxs-lookup"><span data-stu-id="91085-193">IIS 7.0: Configure SMTP E-Mail</span></span>](https://go.microsoft.com/fwlink/?LinkId=150457)  
  
- [<span data-ttu-id="91085-194">Cómo instalar el servicio SMTP</span><span class="sxs-lookup"><span data-stu-id="91085-194">How to Install the SMTP Service</span></span>](https://go.microsoft.com/fwlink/?LinkId=150458)  
  
 <span data-ttu-id="91085-195">Hay disponibles para descarga emuladores de SMTP proporcionados por terceros.</span><span class="sxs-lookup"><span data-stu-id="91085-195">SMTP emulators provided by third parties are available for download.</span></span>  
  
##### <a name="to-run-this-sample"></a><span data-ttu-id="91085-196">Para ejecutar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="91085-196">To run this sample</span></span>  
  
1. <span data-ttu-id="91085-197">Con Visual Studio 2010, abra el archivo de solución SendMail. sln.</span><span class="sxs-lookup"><span data-stu-id="91085-197">Using Visual Studio 2010, open the SendMail.sln solution file.</span></span>  
  
2. <span data-ttu-id="91085-198">Asegúrese de que tiene acceso a un servidor SMTP válido.</span><span class="sxs-lookup"><span data-stu-id="91085-198">Ensure that you have access to a valid SMTP server.</span></span> <span data-ttu-id="91085-199">Vea las instrucciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="91085-199">See the set-up instructions.</span></span>  
  
3. <span data-ttu-id="91085-200">Configure el programa con la dirección del servidor y desde y hacia las direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="91085-200">Configure the program with your server address, and From and To email addresses.</span></span>  
  
     <span data-ttu-id="91085-201">Para ejecutar correctamente este ejemplo, es posible que necesite configurar el valor de desde y para las direcciones de correo electrónico y la dirección del servidor SMTP en Program.cs y en Sequence. Xaml.</span><span class="sxs-lookup"><span data-stu-id="91085-201">To correctly run this sample, you may need to configure the value of From and To email addresses and the address of the SMTP server in  Program.cs and in Sequence.xaml.</span></span> <span data-ttu-id="91085-202">Necesitará cambiar la dirección en ambas ubicaciones, dado que el programa envía el correo de dos maneras diferentes</span><span class="sxs-lookup"><span data-stu-id="91085-202">You will need to change the address in both locations since the program sends mail in two different ways</span></span>  
  
4. <span data-ttu-id="91085-203">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="91085-203">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5. <span data-ttu-id="91085-204">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="91085-204">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="91085-205">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="91085-205">The samples may already be installed on your machine.</span></span> <span data-ttu-id="91085-206">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="91085-206">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="91085-207">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91085-207">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="91085-208">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="91085-208">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`
