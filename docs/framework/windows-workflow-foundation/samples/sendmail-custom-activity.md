---
title: Actividad personalizada SendMail
ms.date: 03/30/2017
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
ms.openlocfilehash: 4dca15bfd3798b9282960663bea827f9323a1266
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547745"
---
# <a name="sendmail-custom-activity"></a><span data-ttu-id="9e415-102">Actividad personalizada SendMail</span><span class="sxs-lookup"><span data-stu-id="9e415-102">SendMail Custom Activity</span></span>
<span data-ttu-id="9e415-103">En este ejemplo se muestra cómo crear una actividad personalizada que deriva de <xref:System.Activities.AsyncCodeActivity> para enviar correo utilizando SMTP para el uso dentro de una aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9e415-103">This sample demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span> <span data-ttu-id="9e415-104">La actividad personalizada utiliza las capacidades de <xref:System.Net.Mail.SmtpClient> para enviar correo electrónico de forma asincrónica y enviar correo con autenticación.</span><span class="sxs-lookup"><span data-stu-id="9e415-104">The custom activity uses the capabilities of <xref:System.Net.Mail.SmtpClient> to send email asynchronously and to send mail with authentication.</span></span> <span data-ttu-id="9e415-105">También proporciona algunas características de usuario final como el modo de prueba, reemplazo del token, plantillas de archivo y ruta de colocación para dejar la prueba.</span><span class="sxs-lookup"><span data-stu-id="9e415-105">It also provides some end-user features like test mode, token replacement, file templates, and test drop path.</span></span>  
  
 <span data-ttu-id="9e415-106">En la siguiente tabla se detallan los argumentos de la actividad `SendMail`.</span><span class="sxs-lookup"><span data-stu-id="9e415-106">The following table details the arguments for the `SendMail` activity.</span></span>  
  
|<span data-ttu-id="9e415-107">Nombre</span><span class="sxs-lookup"><span data-stu-id="9e415-107">Name</span></span>|<span data-ttu-id="9e415-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="9e415-108">Type</span></span>|<span data-ttu-id="9e415-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e415-109">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9e415-110">Host</span><span class="sxs-lookup"><span data-stu-id="9e415-110">Host</span></span>|<span data-ttu-id="9e415-111">String</span><span class="sxs-lookup"><span data-stu-id="9e415-111">String</span></span>|<span data-ttu-id="9e415-112">Dirección del host del servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="9e415-112">Address of the SMTP server host.</span></span>|  
|<span data-ttu-id="9e415-113">Puerto</span><span class="sxs-lookup"><span data-stu-id="9e415-113">Port</span></span>|<span data-ttu-id="9e415-114">String</span><span class="sxs-lookup"><span data-stu-id="9e415-114">String</span></span>|<span data-ttu-id="9e415-115">El puerto del servicio SMTP en el host.</span><span class="sxs-lookup"><span data-stu-id="9e415-115">Port of the SMTP service in the host.</span></span>|  
|<span data-ttu-id="9e415-116">EnableSsl</span><span class="sxs-lookup"><span data-stu-id="9e415-116">EnableSsl</span></span>|<span data-ttu-id="9e415-117">bool</span><span class="sxs-lookup"><span data-stu-id="9e415-117">bool</span></span>|<span data-ttu-id="9e415-118">Especifica si el objeto <xref:System.Net.Mail.SmtpClient> utiliza SSL (Secure Sockets Layer) para cifrar la conexión.</span><span class="sxs-lookup"><span data-stu-id="9e415-118">Specifies whether the <xref:System.Net.Mail.SmtpClient> uses Secure Sockets Layer (SSL) to encrypt the connection.</span></span>|  
|<span data-ttu-id="9e415-119">UserName</span><span class="sxs-lookup"><span data-stu-id="9e415-119">UserName</span></span>|<span data-ttu-id="9e415-120">String</span><span class="sxs-lookup"><span data-stu-id="9e415-120">String</span></span>|<span data-ttu-id="9e415-121">Nombre de usuario para preparar las credenciales para autenticar la propiedad <xref:System.Net.Mail.SmtpClient.Credentials%2A> del remitente.</span><span class="sxs-lookup"><span data-stu-id="9e415-121">Username to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="9e415-122">Contraseña</span><span class="sxs-lookup"><span data-stu-id="9e415-122">Password</span></span>|<span data-ttu-id="9e415-123">String</span><span class="sxs-lookup"><span data-stu-id="9e415-123">String</span></span>|<span data-ttu-id="9e415-124">Contraseña para preparar las credenciales para autenticar la propiedad <xref:System.Net.Mail.SmtpClient.Credentials%2A> del remitente.</span><span class="sxs-lookup"><span data-stu-id="9e415-124">Password to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="9e415-125">Asunto</span><span class="sxs-lookup"><span data-stu-id="9e415-125">Subject</span></span>|<xref:System.Activities.InArgument%601>\<string>|<span data-ttu-id="9e415-126">Asunto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9e415-126">Subject of the message.</span></span>|  
|<span data-ttu-id="9e415-127">Body</span><span class="sxs-lookup"><span data-stu-id="9e415-127">Body</span></span>|<xref:System.Activities.InArgument%601>\<string>|<span data-ttu-id="9e415-128">Cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9e415-128">Body of the message.</span></span>|  
|<span data-ttu-id="9e415-129">Datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="9e415-129">Attachments</span></span>|<xref:System.Activities.InArgument%601>\<string>|<span data-ttu-id="9e415-130">Colección de datos adjuntos usada para almacenar datos adjuntos a este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9e415-130">Attachment collection used to store data attached to this email message.</span></span>|  
|<span data-ttu-id="9e415-131">From</span><span class="sxs-lookup"><span data-stu-id="9e415-131">From</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="9e415-132">Dirección de este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9e415-132">From address for this email message.</span></span>|  
|<span data-ttu-id="9e415-133">En</span><span class="sxs-lookup"><span data-stu-id="9e415-133">To</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="9e415-134">Colección de direcciones que contiene los destinatarios de este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9e415-134">Address collection that contains the recipients of this email message.</span></span>|  
|<span data-ttu-id="9e415-135">CC</span><span class="sxs-lookup"><span data-stu-id="9e415-135">CC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="9e415-136">Colección de direcciones que contiene los destinatarios de copia carbón (CC) de este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9e415-136">Address collection that contains the carbon copy (CC) recipients for this email message.</span></span>|  
|<span data-ttu-id="9e415-137">BCC</span><span class="sxs-lookup"><span data-stu-id="9e415-137">BCC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="9e415-138">Colección de direcciones que contiene los destinatarios de copia carbón oculta (CCO) de este mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9e415-138">Address collection that contains the blind carbon copy (BCC) recipients for this email message.</span></span>|  
|<span data-ttu-id="9e415-139">Tokens</span><span class="sxs-lookup"><span data-stu-id="9e415-139">Tokens</span></span>|<span data-ttu-id="9e415-140"><xref:System.Activities.InArgument%601><IDictionary\<string, string>></span><span class="sxs-lookup"><span data-stu-id="9e415-140"><xref:System.Activities.InArgument%601><IDictionary\<string, string>></span></span>|<span data-ttu-id="9e415-141">Tokens para reemplazar en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="9e415-141">Tokens to replace in the body.</span></span> <span data-ttu-id="9e415-142">Esta característica les permite a los usuarios especificar algunos valores del cuerpo que pueden ser reemplazados después por los tokens que proporcionó utilizando esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="9e415-142">This feature allows users to specify some values in the body than can be replaced later by the tokens provided using this property.</span></span>|  
|<span data-ttu-id="9e415-143">BodyTemplateFilePath</span><span class="sxs-lookup"><span data-stu-id="9e415-143">BodyTemplateFilePath</span></span>|<span data-ttu-id="9e415-144">String</span><span class="sxs-lookup"><span data-stu-id="9e415-144">String</span></span>|<span data-ttu-id="9e415-145">Ruta de acceso de una plantilla para el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="9e415-145">Path of a template for the body.</span></span> <span data-ttu-id="9e415-146">La actividad `SendMail` copia el contenido de este archivo en su propiedad de cuerpo.</span><span class="sxs-lookup"><span data-stu-id="9e415-146">The `SendMail` activity copies the contents of this file to its body property.</span></span><br /><br /> <span data-ttu-id="9e415-147">La plantilla puede contener tokens que son reemplazados por el contenido de la propiedad de tokens.</span><span class="sxs-lookup"><span data-stu-id="9e415-147">The template can contain tokens that are replaced by the contents of the tokens property.</span></span>|  
|<span data-ttu-id="9e415-148">TestMailTo</span><span class="sxs-lookup"><span data-stu-id="9e415-148">TestMailTo</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="9e415-149">Cuando se establece esta propiedad, todos los correos electrónicos se envían a la dirección especificada en él.</span><span class="sxs-lookup"><span data-stu-id="9e415-149">When this property is set, all emails are sent to the address specified in it.</span></span><br /><br /> <span data-ttu-id="9e415-150">Se pretende que esta propiedad sea utilizada al probar los flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9e415-150">This property is intended to be used when testing workflows.</span></span> <span data-ttu-id="9e415-151">Por ejemplo, si desea asegurarse de que todos los mensajes de correo electrónico se envían sin enviarlos a los destinatarios reales.</span><span class="sxs-lookup"><span data-stu-id="9e415-151">For example, when you want to make sure that all emails are sent without sending them to the actual recipients.</span></span>|  
|<span data-ttu-id="9e415-152">TestDropPath</span><span class="sxs-lookup"><span data-stu-id="9e415-152">TestDropPath</span></span>|<span data-ttu-id="9e415-153">String</span><span class="sxs-lookup"><span data-stu-id="9e415-153">String</span></span>|<span data-ttu-id="9e415-154">Cuando se establece esta propiedad, todos los correos electrónicos también se guardan en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="9e415-154">When this property is set, all emails are also saved in the specified file.</span></span><br /><br /> <span data-ttu-id="9e415-155">Esta propiedad está pensada para usarse al probar o Depurar flujos de trabajo, para asegurarse de que el formato y el contenido de los mensajes de correo electrónico salientes es adecuado.</span><span class="sxs-lookup"><span data-stu-id="9e415-155">This property is intended to be used when you are testing or debugging workflows, to make sure that the format and contents of the outgoing emails is appropriate.</span></span>|  
  
## <a name="solution-contents"></a><span data-ttu-id="9e415-156">Contenido de la solución</span><span class="sxs-lookup"><span data-stu-id="9e415-156">Solution Contents</span></span>  
 <span data-ttu-id="9e415-157">La solución contiene dos proyectos.</span><span class="sxs-lookup"><span data-stu-id="9e415-157">The solution contains two projects.</span></span>  
  
|<span data-ttu-id="9e415-158">Proyecto</span><span class="sxs-lookup"><span data-stu-id="9e415-158">Project</span></span>|<span data-ttu-id="9e415-159">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e415-159">Description</span></span>|<span data-ttu-id="9e415-160">Archivos importantes</span><span class="sxs-lookup"><span data-stu-id="9e415-160">Important Files</span></span>|  
|-------------|-----------------|---------------------|  
|<span data-ttu-id="9e415-161">SendMail</span><span class="sxs-lookup"><span data-stu-id="9e415-161">SendMail</span></span>|<span data-ttu-id="9e415-162">La actividad SendMail</span><span class="sxs-lookup"><span data-stu-id="9e415-162">The SendMail activity</span></span>|<span data-ttu-id="9e415-163">1. SendMail.cs: implementación para la actividad principal</span><span class="sxs-lookup"><span data-stu-id="9e415-163">1.  SendMail.cs: implementation for the main activity</span></span><br /><span data-ttu-id="9e415-164">2. SendMailDesigner. XAML y SendMailDesigner.xaml.cs: diseñador para la actividad SendMail</span><span class="sxs-lookup"><span data-stu-id="9e415-164">2.  SendMailDesigner.xaml and SendMailDesigner.xaml.cs: designer for the SendMail activity</span></span><br /><span data-ttu-id="9e415-165">3. MailTemplateBody.htm: plantilla para el correo electrónico que se va a enviar.</span><span class="sxs-lookup"><span data-stu-id="9e415-165">3.  MailTemplateBody.htm: template for the email to be sent out.</span></span>|  
|<span data-ttu-id="9e415-166">SendMailTestClient</span><span class="sxs-lookup"><span data-stu-id="9e415-166">SendMailTestClient</span></span>|<span data-ttu-id="9e415-167">Cliente para probar la actividad SendMail.</span><span class="sxs-lookup"><span data-stu-id="9e415-167">Client to test the SendMail activity.</span></span>  <span data-ttu-id="9e415-168">Este proyecto muestra dos maneras de invocar la actividad SendMail: mediante declaración y mediante programación.</span><span class="sxs-lookup"><span data-stu-id="9e415-168">This project demonstrates two ways of invoking the SendMail activity: declaratively, and programmatically.</span></span>|<span data-ttu-id="9e415-169">1. Sequence1. XAML: flujo de trabajo que invoca la actividad SendMail.</span><span class="sxs-lookup"><span data-stu-id="9e415-169">1.  Sequence1.xaml: workflow that invokes the SendMail activity.</span></span><br /><span data-ttu-id="9e415-170">2. Program.cs: invoca Sequence1 y también crea un flujo de trabajo mediante programación que usa SendMail.</span><span class="sxs-lookup"><span data-stu-id="9e415-170">2.  Program.cs: invokes Sequence1 and also creates a workflow programmatically that uses SendMail.</span></span>|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a><span data-ttu-id="9e415-171">Nueva configuración de la actividad SendMail</span><span class="sxs-lookup"><span data-stu-id="9e415-171">Further configuration of the SendMail activity</span></span>  
 <span data-ttu-id="9e415-172">Aunque no se muestra en el ejemplo, los usuarios pueden realizar una configuración adicional de la actividad SendMail.</span><span class="sxs-lookup"><span data-stu-id="9e415-172">Although not shown in the sample, users can perform addition configuration of the SendMail activity.</span></span> <span data-ttu-id="9e415-173">Las tres secciones siguientes muestran cómo se hace esto.</span><span class="sxs-lookup"><span data-stu-id="9e415-173">The next three sections demonstrate how this is done.</span></span>  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a><span data-ttu-id="9e415-174">Enviar un correo electrónico mediante los tokens especificados en el cuerpo</span><span class="sxs-lookup"><span data-stu-id="9e415-174">Sending an email using tokens specified in the body</span></span>  
 <span data-ttu-id="9e415-175">Este fragmento de código muestra cómo puede enviar el correo electrónico con tokens en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="9e415-175">This code snippet demonstrates how you can send email with tokens in the body.</span></span> <span data-ttu-id="9e415-176">Observe que los tokens se proporcionan en la propiedad del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="9e415-176">Notice how the tokens are provided in the body property.</span></span> <span data-ttu-id="9e415-177">Los valores para esos tokens se proporcionan a la propiedad de tokens.</span><span class="sxs-lookup"><span data-stu-id="9e415-177">Values for those tokens are provided to the tokens property.</span></span>  
  
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
  
### <a name="sending-an-email-using-a-template"></a><span data-ttu-id="9e415-178">Enviar un correo electrónico mediante una plantilla</span><span class="sxs-lookup"><span data-stu-id="9e415-178">Sending an email using a template</span></span>  
 <span data-ttu-id="9e415-179">Este fragmento de código muestra cómo enviar un correo electrónico utilizando tokens de la plantilla en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="9e415-179">This snippet shows how to send an email using a template tokens in the body.</span></span> <span data-ttu-id="9e415-180">Observe que al establecer la propiedad `BodyTemplateFilePath` no necesitamos proporcionar el valor de la propiedad Body (el contenido del archivo de plantilla se copiará en el cuerpo).</span><span class="sxs-lookup"><span data-stu-id="9e415-180">Notice that when setting the `BodyTemplateFilePath` property we don’t need to provide the value for Body property (the contents of the template file will be copied to the body).</span></span>  
  
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
  
### <a name="sending-mails-in-testing-mode"></a><span data-ttu-id="9e415-181">Enviar correo en modo de prueba</span><span class="sxs-lookup"><span data-stu-id="9e415-181">Sending Mails in Testing Mode</span></span>  
 <span data-ttu-id="9e415-182">Este fragmento de código muestra cómo establecer las dos propiedades de prueba: al establecer `TestMailTo` en todos los mensajes se enviará a `john.doe@contoso.con` (sin tener en cuenta los valores de para, CC, CCO).</span><span class="sxs-lookup"><span data-stu-id="9e415-182">This code snippet shows how to set the two testing properties: by setting `TestMailTo` to all messages will be sent to `john.doe@contoso.con` (without regard of the values of To, Cc, Bcc).</span></span> <span data-ttu-id="9e415-183">Estableciendo que todos los correos electrónicos de salida a TestDropPath se registrarán también en la ruta de acceso proporcionada.</span><span class="sxs-lookup"><span data-stu-id="9e415-183">By setting TestDropPath all outgoing emails will be also recorded in the provided path.</span></span> <span data-ttu-id="9e415-184">Estas propiedades se pueden establecer independientemente (no están relacionadas).</span><span class="sxs-lookup"><span data-stu-id="9e415-184">These properties can be set independently (they are not related).</span></span>  
  
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
  
## <a name="set-up-instructions"></a><span data-ttu-id="9e415-185">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="9e415-185">Set-Up Instructions</span></span>  
 <span data-ttu-id="9e415-186">En este ejemplo se requiere acceso a un servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="9e415-186">Access to a SMTP server is required for this sample.</span></span>  
  
 <span data-ttu-id="9e415-187">Para obtener más información acerca de cómo configurar un servidor SMTP, consulte los siguientes vínculos.</span><span class="sxs-lookup"><span data-stu-id="9e415-187">For more information about setting up a SMTP server, see the following links.</span></span>  
  
- <span data-ttu-id="9e415-188">[Configurar el servicio SMTP (IIS 6.0)](/previous-versions/windows/it-pro/windows-server-2003/cc784968(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="9e415-188">[Configuring the SMTP Service (IIS 6.0)](/previous-versions/windows/it-pro/windows-server-2003/cc784968(v=ws.10))</span></span>  
  
- <span data-ttu-id="9e415-189">[IIS 7.0: configurar correo electrónico de SMTP](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772058(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="9e415-189">[IIS 7.0: Configure SMTP E-Mail](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772058(v=ws.10))</span></span>  
  
- <span data-ttu-id="9e415-190">[Cómo instalar el servicio SMTP](/previous-versions/tn-archive/aa997480(v=exchg.65))</span><span class="sxs-lookup"><span data-stu-id="9e415-190">[How to Install the SMTP Service](/previous-versions/tn-archive/aa997480(v=exchg.65))</span></span>  
  
 <span data-ttu-id="9e415-191">Hay disponibles para descarga emuladores de SMTP proporcionados por terceros.</span><span class="sxs-lookup"><span data-stu-id="9e415-191">SMTP emulators provided by third parties are available for download.</span></span>  
  
##### <a name="to-run-this-sample"></a><span data-ttu-id="9e415-192">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="9e415-192">To run this sample</span></span>  
  
1. <span data-ttu-id="9e415-193">Con Visual Studio 2010, abra el archivo de solución SendMail. sln.</span><span class="sxs-lookup"><span data-stu-id="9e415-193">Using Visual Studio 2010, open the SendMail.sln solution file.</span></span>  
  
2. <span data-ttu-id="9e415-194">Asegúrese de que tiene acceso a un servidor SMTP válido.</span><span class="sxs-lookup"><span data-stu-id="9e415-194">Ensure that you have access to a valid SMTP server.</span></span> <span data-ttu-id="9e415-195">Vea las instrucciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="9e415-195">See the set-up instructions.</span></span>  
  
3. <span data-ttu-id="9e415-196">Configure el programa con la dirección del servidor y desde y hacia las direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9e415-196">Configure the program with your server address, and From and To email addresses.</span></span>  
  
     <span data-ttu-id="9e415-197">Para ejecutar correctamente este ejemplo, es posible que necesite configurar el valor de desde y para las direcciones de correo electrónico y la dirección del servidor SMTP en Program.cs y en Sequence. Xaml.</span><span class="sxs-lookup"><span data-stu-id="9e415-197">To correctly run this sample, you may need to configure the value of From and To email addresses and the address of the SMTP server in  Program.cs and in Sequence.xaml.</span></span> <span data-ttu-id="9e415-198">Necesitará cambiar la dirección en ambas ubicaciones, dado que el programa envía el correo de dos maneras diferentes</span><span class="sxs-lookup"><span data-stu-id="9e415-198">You will need to change the address in both locations since the program sends mail in two different ways</span></span>  
  
4. <span data-ttu-id="9e415-199">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="9e415-199">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5. <span data-ttu-id="9e415-200">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="9e415-200">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9e415-201">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="9e415-201">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9e415-202">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="9e415-202">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="9e415-203">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="9e415-203">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9e415-204">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="9e415-204">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`
