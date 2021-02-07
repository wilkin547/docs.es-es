---
description: 'Más información sobre: actividad personalizada SendMail'
title: Actividad personalizada SendMail
ms.date: 03/30/2017
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
ms.openlocfilehash: 853e28d26c41338670d377593d5a3536b011d112
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741762"
---
# <a name="sendmail-custom-activity"></a><span data-ttu-id="c6f04-103">Actividad personalizada SendMail</span><span class="sxs-lookup"><span data-stu-id="c6f04-103">SendMail Custom Activity</span></span>

<span data-ttu-id="c6f04-104">En este ejemplo se muestra cómo crear una actividad personalizada que deriva de <xref:System.Activities.AsyncCodeActivity> para enviar correo utilizando SMTP para el uso dentro de una aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c6f04-104">This sample demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span> <span data-ttu-id="c6f04-105">La actividad personalizada utiliza las capacidades de <xref:System.Net.Mail.SmtpClient> para enviar correo electrónico de forma asincrónica y enviar correo con autenticación.</span><span class="sxs-lookup"><span data-stu-id="c6f04-105">The custom activity uses the capabilities of <xref:System.Net.Mail.SmtpClient> to send email asynchronously and to send mail with authentication.</span></span> <span data-ttu-id="c6f04-106">También proporciona algunas características de usuario final como el modo de prueba, reemplazo del token, plantillas de archivo y ruta de colocación para dejar la prueba.</span><span class="sxs-lookup"><span data-stu-id="c6f04-106">It also provides some end-user features like test mode, token replacement, file templates, and test drop path.</span></span>  
  
 <span data-ttu-id="c6f04-107">En la siguiente tabla se detallan los argumentos de la actividad `SendMail`.</span><span class="sxs-lookup"><span data-stu-id="c6f04-107">The following table details the arguments for the `SendMail` activity.</span></span>  
  
|<span data-ttu-id="c6f04-108">Nombre</span><span class="sxs-lookup"><span data-stu-id="c6f04-108">Name</span></span>|<span data-ttu-id="c6f04-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="c6f04-109">Type</span></span>|<span data-ttu-id="c6f04-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c6f04-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="c6f04-111">Host</span><span class="sxs-lookup"><span data-stu-id="c6f04-111">Host</span></span>|<span data-ttu-id="c6f04-112">String</span><span class="sxs-lookup"><span data-stu-id="c6f04-112">String</span></span>|<span data-ttu-id="c6f04-113">Dirección del host del servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="c6f04-113">Address of the SMTP server host.</span></span>|  
|<span data-ttu-id="c6f04-114">Puerto</span><span class="sxs-lookup"><span data-stu-id="c6f04-114">Port</span></span>|<span data-ttu-id="c6f04-115">String</span><span class="sxs-lookup"><span data-stu-id="c6f04-115">String</span></span>|<span data-ttu-id="c6f04-116">El puerto del servicio SMTP en el host.</span><span class="sxs-lookup"><span data-stu-id="c6f04-116">Port of the SMTP service in the host.</span></span>|  
|<span data-ttu-id="c6f04-117">EnableSsl</span><span class="sxs-lookup"><span data-stu-id="c6f04-117">EnableSsl</span></span>|<span data-ttu-id="c6f04-118">bool</span><span class="sxs-lookup"><span data-stu-id="c6f04-118">bool</span></span>|<span data-ttu-id="c6f04-119">Especifica si el objeto <xref:System.Net.Mail.SmtpClient> utiliza SSL (Secure Sockets Layer) para cifrar la conexión.</span><span class="sxs-lookup"><span data-stu-id="c6f04-119">Specifies whether the <xref:System.Net.Mail.SmtpClient> uses Secure Sockets Layer (SSL) to encrypt the connection.</span></span>|  
|<span data-ttu-id="c6f04-120">UserName</span><span class="sxs-lookup"><span data-stu-id="c6f04-120">UserName</span></span>|<span data-ttu-id="c6f04-121">String</span><span class="sxs-lookup"><span data-stu-id="c6f04-121">String</span></span>|<span data-ttu-id="c6f04-122">Nombre de usuario para preparar las credenciales para autenticar la propiedad <xref:System.Net.Mail.SmtpClient.Credentials%2A> del remitente.</span><span class="sxs-lookup"><span data-stu-id="c6f04-122">Username to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="c6f04-123">Contraseña</span><span class="sxs-lookup"><span data-stu-id="c6f04-123">Password</span></span>|<span data-ttu-id="c6f04-124">String</span><span class="sxs-lookup"><span data-stu-id="c6f04-124">String</span></span>|<span data-ttu-id="c6f04-125">Contraseña para preparar las credenciales para autenticar la propiedad <xref:System.Net.Mail.SmtpClient.Credentials%2A> del remitente.</span><span class="sxs-lookup"><span data-stu-id="c6f04-125">Password to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="c6f04-126">Asunto</span><span class="sxs-lookup"><span data-stu-id="c6f04-126">Subject</span></span>|<xref:System.Activities.InArgument%601>\<string>|<span data-ttu-id="c6f04-127">Asunto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c6f04-127">Subject of the message.</span></span>|  
|<span data-ttu-id="c6f04-128">Cuerpo</span><span class="sxs-lookup"><span data-stu-id="c6f04-128">Body</span></span>|<xref:System.Activities.InArgument%601>\<string>|<span data-ttu-id="c6f04-129">Cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c6f04-129">Body of the message.</span></span>|  
|<span data-ttu-id="c6f04-130">Datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="c6f04-130">Attachments</span></span>|<xref:System.Activities.InArgument%601>\<string>|<span data-ttu-id="c6f04-131">Colección de datos adjuntos usada para almacenar datos adjuntos a este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c6f04-131">Attachment collection used to store data attached to this email message.</span></span>|  
|<span data-ttu-id="c6f04-132">From</span><span class="sxs-lookup"><span data-stu-id="c6f04-132">From</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="c6f04-133">Dirección de este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c6f04-133">From address for this email message.</span></span>|  
|<span data-ttu-id="c6f04-134">En</span><span class="sxs-lookup"><span data-stu-id="c6f04-134">To</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="c6f04-135">Colección de direcciones que contiene los destinatarios de este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c6f04-135">Address collection that contains the recipients of this email message.</span></span>|  
|<span data-ttu-id="c6f04-136">CC</span><span class="sxs-lookup"><span data-stu-id="c6f04-136">CC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="c6f04-137">Colección de direcciones que contiene los destinatarios de copia carbón (CC) de este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c6f04-137">Address collection that contains the carbon copy (CC) recipients for this email message.</span></span>|  
|<span data-ttu-id="c6f04-138">BCC</span><span class="sxs-lookup"><span data-stu-id="c6f04-138">BCC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="c6f04-139">Colección de direcciones que contiene los destinatarios de copia carbón oculta (CCO) de este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c6f04-139">Address collection that contains the blind carbon copy (BCC) recipients for this email message.</span></span>|  
|<span data-ttu-id="c6f04-140">Tokens</span><span class="sxs-lookup"><span data-stu-id="c6f04-140">Tokens</span></span>|<span data-ttu-id="c6f04-141"><xref:System.Activities.InArgument%601><IDictionary\<string, string>></span><span class="sxs-lookup"><span data-stu-id="c6f04-141"><xref:System.Activities.InArgument%601><IDictionary\<string, string>></span></span>|<span data-ttu-id="c6f04-142">Tokens para reemplazar en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="c6f04-142">Tokens to replace in the body.</span></span> <span data-ttu-id="c6f04-143">Esta característica les permite a los usuarios especificar algunos valores del cuerpo que pueden ser reemplazados después por los tokens que proporcionó utilizando esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="c6f04-143">This feature allows users to specify some values in the body than can be replaced later by the tokens provided using this property.</span></span>|  
|<span data-ttu-id="c6f04-144">BodyTemplateFilePath</span><span class="sxs-lookup"><span data-stu-id="c6f04-144">BodyTemplateFilePath</span></span>|<span data-ttu-id="c6f04-145">String</span><span class="sxs-lookup"><span data-stu-id="c6f04-145">String</span></span>|<span data-ttu-id="c6f04-146">Ruta de acceso de una plantilla para el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="c6f04-146">Path of a template for the body.</span></span> <span data-ttu-id="c6f04-147">La actividad `SendMail` copia el contenido de este archivo en su propiedad de cuerpo.</span><span class="sxs-lookup"><span data-stu-id="c6f04-147">The `SendMail` activity copies the contents of this file to its body property.</span></span><br /><br /> <span data-ttu-id="c6f04-148">La plantilla puede contener tokens que son reemplazados por el contenido de la propiedad de tokens.</span><span class="sxs-lookup"><span data-stu-id="c6f04-148">The template can contain tokens that are replaced by the contents of the tokens property.</span></span>|  
|<span data-ttu-id="c6f04-149">TestMailTo</span><span class="sxs-lookup"><span data-stu-id="c6f04-149">TestMailTo</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="c6f04-150">Cuando se establece esta propiedad, todos los correos electrónicos se envían a la dirección especificada en él.</span><span class="sxs-lookup"><span data-stu-id="c6f04-150">When this property is set, all emails are sent to the address specified in it.</span></span><br /><br /> <span data-ttu-id="c6f04-151">Se pretende que esta propiedad sea utilizada al probar los flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c6f04-151">This property is intended to be used when testing workflows.</span></span> <span data-ttu-id="c6f04-152">Por ejemplo, si desea asegurarse de que todos los mensajes de correo electrónico se envían sin enviarlos a los destinatarios reales.</span><span class="sxs-lookup"><span data-stu-id="c6f04-152">For example, when you want to make sure that all emails are sent without sending them to the actual recipients.</span></span>|  
|<span data-ttu-id="c6f04-153">TestDropPath</span><span class="sxs-lookup"><span data-stu-id="c6f04-153">TestDropPath</span></span>|<span data-ttu-id="c6f04-154">String</span><span class="sxs-lookup"><span data-stu-id="c6f04-154">String</span></span>|<span data-ttu-id="c6f04-155">Cuando se establece esta propiedad, todos los correos electrónicos también se guardan en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="c6f04-155">When this property is set, all emails are also saved in the specified file.</span></span><br /><br /> <span data-ttu-id="c6f04-156">Esta propiedad está pensada para usarse al probar o Depurar flujos de trabajo, para asegurarse de que el formato y el contenido de los mensajes de correo electrónico salientes es adecuado.</span><span class="sxs-lookup"><span data-stu-id="c6f04-156">This property is intended to be used when you are testing or debugging workflows, to make sure that the format and contents of the outgoing emails is appropriate.</span></span>|  
  
## <a name="solution-contents"></a><span data-ttu-id="c6f04-157">Contenido de la solución</span><span class="sxs-lookup"><span data-stu-id="c6f04-157">Solution Contents</span></span>  

 <span data-ttu-id="c6f04-158">La solución contiene dos proyectos.</span><span class="sxs-lookup"><span data-stu-id="c6f04-158">The solution contains two projects.</span></span>  
  
|<span data-ttu-id="c6f04-159">Proyecto</span><span class="sxs-lookup"><span data-stu-id="c6f04-159">Project</span></span>|<span data-ttu-id="c6f04-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="c6f04-160">Description</span></span>|<span data-ttu-id="c6f04-161">Archivos importantes</span><span class="sxs-lookup"><span data-stu-id="c6f04-161">Important Files</span></span>|  
|-------------|-----------------|---------------------|  
|<span data-ttu-id="c6f04-162">SendMail</span><span class="sxs-lookup"><span data-stu-id="c6f04-162">SendMail</span></span>|<span data-ttu-id="c6f04-163">La actividad SendMail</span><span class="sxs-lookup"><span data-stu-id="c6f04-163">The SendMail activity</span></span>|<span data-ttu-id="c6f04-164">1. SendMail.cs: implementación para la actividad principal</span><span class="sxs-lookup"><span data-stu-id="c6f04-164">1.  SendMail.cs: implementation for the main activity</span></span><br /><span data-ttu-id="c6f04-165">2. SendMailDesigner. XAML y SendMailDesigner.xaml.cs: diseñador para la actividad SendMail</span><span class="sxs-lookup"><span data-stu-id="c6f04-165">2.  SendMailDesigner.xaml and SendMailDesigner.xaml.cs: designer for the SendMail activity</span></span><br /><span data-ttu-id="c6f04-166">3. MailTemplateBody.htm: plantilla para el correo electrónico que se va a enviar.</span><span class="sxs-lookup"><span data-stu-id="c6f04-166">3.  MailTemplateBody.htm: template for the email to be sent out.</span></span>|  
|<span data-ttu-id="c6f04-167">SendMailTestClient</span><span class="sxs-lookup"><span data-stu-id="c6f04-167">SendMailTestClient</span></span>|<span data-ttu-id="c6f04-168">Cliente para probar la actividad SendMail.</span><span class="sxs-lookup"><span data-stu-id="c6f04-168">Client to test the SendMail activity.</span></span>  <span data-ttu-id="c6f04-169">Este proyecto muestra dos maneras de invocar la actividad SendMail: mediante declaración y mediante programación.</span><span class="sxs-lookup"><span data-stu-id="c6f04-169">This project demonstrates two ways of invoking the SendMail activity: declaratively, and programmatically.</span></span>|<span data-ttu-id="c6f04-170">1. Sequence1. XAML: flujo de trabajo que invoca la actividad SendMail.</span><span class="sxs-lookup"><span data-stu-id="c6f04-170">1.  Sequence1.xaml: workflow that invokes the SendMail activity.</span></span><br /><span data-ttu-id="c6f04-171">2. Program.cs: invoca Sequence1 y también crea un flujo de trabajo mediante programación que usa SendMail.</span><span class="sxs-lookup"><span data-stu-id="c6f04-171">2.  Program.cs: invokes Sequence1 and also creates a workflow programmatically that uses SendMail.</span></span>|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a><span data-ttu-id="c6f04-172">Nueva configuración de la actividad SendMail</span><span class="sxs-lookup"><span data-stu-id="c6f04-172">Further configuration of the SendMail activity</span></span>  

 <span data-ttu-id="c6f04-173">Aunque no se muestra en el ejemplo, los usuarios pueden realizar una configuración adicional de la actividad SendMail.</span><span class="sxs-lookup"><span data-stu-id="c6f04-173">Although not shown in the sample, users can perform addition configuration of the SendMail activity.</span></span> <span data-ttu-id="c6f04-174">Las tres secciones siguientes muestran cómo se hace esto.</span><span class="sxs-lookup"><span data-stu-id="c6f04-174">The next three sections demonstrate how this is done.</span></span>  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a><span data-ttu-id="c6f04-175">Enviar un correo electrónico mediante los tokens especificados en el cuerpo</span><span class="sxs-lookup"><span data-stu-id="c6f04-175">Sending an email using tokens specified in the body</span></span>  

 <span data-ttu-id="c6f04-176">Este fragmento de código muestra cómo puede enviar el correo electrónico con tokens en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="c6f04-176">This code snippet demonstrates how you can send email with tokens in the body.</span></span> <span data-ttu-id="c6f04-177">Observe que los tokens se proporcionan en la propiedad del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="c6f04-177">Notice how the tokens are provided in the body property.</span></span> <span data-ttu-id="c6f04-178">Los valores para esos tokens se proporcionan a la propiedad de tokens.</span><span class="sxs-lookup"><span data-stu-id="c6f04-178">Values for those tokens are provided to the tokens property.</span></span>  
  
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
  
### <a name="sending-an-email-using-a-template"></a><span data-ttu-id="c6f04-179">Enviar un correo electrónico mediante una plantilla</span><span class="sxs-lookup"><span data-stu-id="c6f04-179">Sending an email using a template</span></span>  

 <span data-ttu-id="c6f04-180">Este fragmento de código muestra cómo enviar un correo electrónico utilizando tokens de la plantilla en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="c6f04-180">This snippet shows how to send an email using a template tokens in the body.</span></span> <span data-ttu-id="c6f04-181">Observe que al establecer la propiedad `BodyTemplateFilePath` no necesitamos proporcionar el valor de la propiedad Body (el contenido del archivo de plantilla se copiará en el cuerpo).</span><span class="sxs-lookup"><span data-stu-id="c6f04-181">Notice that when setting the `BodyTemplateFilePath` property we don’t need to provide the value for Body property (the contents of the template file will be copied to the body).</span></span>  
  
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
  
### <a name="sending-mails-in-testing-mode"></a><span data-ttu-id="c6f04-182">Enviar correo en modo de prueba</span><span class="sxs-lookup"><span data-stu-id="c6f04-182">Sending Mails in Testing Mode</span></span>  

 <span data-ttu-id="c6f04-183">Este fragmento de código muestra cómo establecer las dos propiedades de prueba: al establecer `TestMailTo` en todos los mensajes se enviará a `john.doe@contoso.con` (sin tener en cuenta los valores de para, CC, CCO).</span><span class="sxs-lookup"><span data-stu-id="c6f04-183">This code snippet shows how to set the two testing properties: by setting `TestMailTo` to all messages will be sent to `john.doe@contoso.con` (without regard of the values of To, Cc, Bcc).</span></span> <span data-ttu-id="c6f04-184">Estableciendo que todos los correos electrónicos de salida a TestDropPath se registrarán también en la ruta de acceso proporcionada.</span><span class="sxs-lookup"><span data-stu-id="c6f04-184">By setting TestDropPath all outgoing emails will be also recorded in the provided path.</span></span> <span data-ttu-id="c6f04-185">Estas propiedades se pueden establecer independientemente (no están relacionadas).</span><span class="sxs-lookup"><span data-stu-id="c6f04-185">These properties can be set independently (they are not related).</span></span>  
  
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
  
## <a name="set-up-instructions"></a><span data-ttu-id="c6f04-186">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="c6f04-186">Set-Up Instructions</span></span>  

 <span data-ttu-id="c6f04-187">En este ejemplo se requiere acceso a un servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="c6f04-187">Access to a SMTP server is required for this sample.</span></span>  
  
 <span data-ttu-id="c6f04-188">Para obtener más información acerca de cómo configurar un servidor SMTP, consulte los siguientes vínculos.</span><span class="sxs-lookup"><span data-stu-id="c6f04-188">For more information about setting up a SMTP server, see the following links.</span></span>  
  
- <span data-ttu-id="c6f04-189">[Configurar el servicio SMTP (IIS 6.0)](/previous-versions/windows/it-pro/windows-server-2003/cc784968(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="c6f04-189">[Configuring the SMTP Service (IIS 6.0)](/previous-versions/windows/it-pro/windows-server-2003/cc784968(v=ws.10))</span></span>  
  
- <span data-ttu-id="c6f04-190">[IIS 7.0: configurar correo electrónico de SMTP](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772058(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="c6f04-190">[IIS 7.0: Configure SMTP E-Mail](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772058(v=ws.10))</span></span>  
  
- <span data-ttu-id="c6f04-191">[Cómo instalar el servicio SMTP](/previous-versions/tn-archive/aa997480(v=exchg.65))</span><span class="sxs-lookup"><span data-stu-id="c6f04-191">[How to Install the SMTP Service](/previous-versions/tn-archive/aa997480(v=exchg.65))</span></span>  
  
 <span data-ttu-id="c6f04-192">Hay disponibles para descarga emuladores de SMTP proporcionados por terceros.</span><span class="sxs-lookup"><span data-stu-id="c6f04-192">SMTP emulators provided by third parties are available for download.</span></span>  
  
##### <a name="to-run-this-sample"></a><span data-ttu-id="c6f04-193">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6f04-193">To run this sample</span></span>  
  
1. <span data-ttu-id="c6f04-194">Con Visual Studio 2010, abra el archivo de solución SendMail. sln.</span><span class="sxs-lookup"><span data-stu-id="c6f04-194">Using Visual Studio 2010, open the SendMail.sln solution file.</span></span>  
  
2. <span data-ttu-id="c6f04-195">Asegúrese de que tiene acceso a un servidor SMTP válido.</span><span class="sxs-lookup"><span data-stu-id="c6f04-195">Ensure that you have access to a valid SMTP server.</span></span> <span data-ttu-id="c6f04-196">Vea las instrucciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="c6f04-196">See the set-up instructions.</span></span>  
  
3. <span data-ttu-id="c6f04-197">Configure el programa con la dirección del servidor y desde y hacia las direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c6f04-197">Configure the program with your server address, and From and To email addresses.</span></span>  
  
     <span data-ttu-id="c6f04-198">Para ejecutar correctamente este ejemplo, es posible que necesite configurar el valor de desde y para las direcciones de correo electrónico y la dirección del servidor SMTP en Program.cs y en Sequence. Xaml.</span><span class="sxs-lookup"><span data-stu-id="c6f04-198">To correctly run this sample, you may need to configure the value of From and To email addresses and the address of the SMTP server in  Program.cs and in Sequence.xaml.</span></span> <span data-ttu-id="c6f04-199">Necesitará cambiar la dirección en ambas ubicaciones, dado que el programa envía el correo de dos maneras diferentes</span><span class="sxs-lookup"><span data-stu-id="c6f04-199">You will need to change the address in both locations since the program sends mail in two different ways</span></span>  
  
4. <span data-ttu-id="c6f04-200">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="c6f04-200">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5. <span data-ttu-id="c6f04-201">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="c6f04-201">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c6f04-202">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="c6f04-202">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c6f04-203">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="c6f04-203">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="c6f04-204">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="c6f04-204">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c6f04-205">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="c6f04-205">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`
