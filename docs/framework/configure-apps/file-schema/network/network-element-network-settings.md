---
title: <network> Elemento (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: c411e00026f03fdb355664049f8db00f3c800352
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219972"
---
# <a name="network-element-network-settings"></a><span data-ttu-id="22a3c-102">\<red > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="22a3c-102">\<network> Element (Network Settings)</span></span>
<span data-ttu-id="22a3c-103">Configura las opciones de red para un servidor de Protocolo Simple de transferencia de correo (SMTP) externo.</span><span class="sxs-lookup"><span data-stu-id="22a3c-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="22a3c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="22a3c-104">\<configuration></span></span>  
<span data-ttu-id="22a3c-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="22a3c-105">\<system.net></span></span>  
<span data-ttu-id="22a3c-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="22a3c-106">\<mailSettings></span></span>  
<span data-ttu-id="22a3c-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="22a3c-107">\<smtp></span></span>  
<span data-ttu-id="22a3c-108">\<network></span><span class="sxs-lookup"><span data-stu-id="22a3c-108">\<network></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22a3c-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22a3c-109">Syntax</span></span>  
  
```xml  
<network  
  clientDomain="string"   
  defaultCredentials="true|false"  
  enableSsl="true|false"  
  host="string"   
  password="string"  
  port="integer"   
  targetName="string"  
  userName="string"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22a3c-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="22a3c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="22a3c-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="22a3c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22a3c-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="22a3c-112">Attributes</span></span>  
  
|<span data-ttu-id="22a3c-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="22a3c-113">Attribute</span></span>|<span data-ttu-id="22a3c-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="22a3c-114">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="22a3c-115">Especifica el nombre de dominio de cliente para usar en la solicitud de protocolo SMTP inicial para conectarse al servidor de correo SMTP.</span><span class="sxs-lookup"><span data-stu-id="22a3c-115">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="22a3c-116">El valor predeterminado es el nombre de host local del equipo local envía la solicitud.</span><span class="sxs-lookup"><span data-stu-id="22a3c-116">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="22a3c-117">Especifica si se deben usar las credenciales de usuario predeterminadas para tener acceso al servidor de correo SMTP para las transacciones SMTP.</span><span class="sxs-lookup"><span data-stu-id="22a3c-117">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="22a3c-118">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="22a3c-118">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="22a3c-119">Especifica si se usa SSL para tener acceso a un servidor de correo SMTP.</span><span class="sxs-lookup"><span data-stu-id="22a3c-119">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="22a3c-120">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="22a3c-120">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="22a3c-121">Especifica el nombre de host del servidor de correo SMTP que se utilizará para las transacciones SMTP.</span><span class="sxs-lookup"><span data-stu-id="22a3c-121">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="22a3c-122">Este atributo tiene ningún valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="22a3c-122">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="22a3c-123">Especifica la contraseña que se utilizará para la autenticación en el servidor de correo SMTP.</span><span class="sxs-lookup"><span data-stu-id="22a3c-123">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="22a3c-124">Este atributo tiene ningún valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="22a3c-124">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="22a3c-125">Especifica el número de puerto para conectarse al servidor de correo SMTP.</span><span class="sxs-lookup"><span data-stu-id="22a3c-125">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="22a3c-126">El valor predeterminado es 25.</span><span class="sxs-lookup"><span data-stu-id="22a3c-126">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="22a3c-127">Especifica el nombre de proveedor de servicio (SPN) que se usará para la autenticación al usar la protección ampliada para las transacciones SMTP.</span><span class="sxs-lookup"><span data-stu-id="22a3c-127">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="22a3c-128">Este atributo tiene ningún valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="22a3c-128">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="22a3c-129">Especifica el nombre de usuario que se usará para la autenticación en el servidor de correo SMTP.</span><span class="sxs-lookup"><span data-stu-id="22a3c-129">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="22a3c-130">Este atributo tiene ningún valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="22a3c-130">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22a3c-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="22a3c-131">Child Elements</span></span>  
 <span data-ttu-id="22a3c-132">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="22a3c-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22a3c-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="22a3c-133">Parent Elements</span></span>  
  
|<span data-ttu-id="22a3c-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="22a3c-134">Element</span></span>|<span data-ttu-id="22a3c-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="22a3c-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22a3c-136">\<SMTP > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="22a3c-136">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="22a3c-137">Configura las opciones de envío de correo de Protocolo Simple de transferencia de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="22a3c-137">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22a3c-138">Comentarios</span><span class="sxs-lookup"><span data-stu-id="22a3c-138">Remarks</span></span>  
 <span data-ttu-id="22a3c-139">Algunos servidores SMTP requieren autenticarse en el servidor antes de su uso.</span><span class="sxs-lookup"><span data-stu-id="22a3c-139">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="22a3c-140">Si desea autenticarse utilizando las credenciales de red predeterminadas en el host, establezca el `defaultCredentials` atributo `true`.</span><span class="sxs-lookup"><span data-stu-id="22a3c-140">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="22a3c-141">El <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> propiedad puede usarse para obtener el valor actual de la `defaultCredentials` atributo desde archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="22a3c-141">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="22a3c-142">También puede usar la autenticación básica (nombre de usuario y contraseña) para autenticarse en el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="22a3c-142">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="22a3c-143">Para usar esta opción, debe especificar un nombre de usuario válido y una contraseña para el servidor SMTP especificado.</span><span class="sxs-lookup"><span data-stu-id="22a3c-143">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22a3c-144">La autenticación básica envía el `userName` y `password` valores sin cifrar al servidor.</span><span class="sxs-lookup"><span data-stu-id="22a3c-144">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="22a3c-145">Cualquiera que controle el tráfico de red puede ver sus credenciales y utilizarlas para conectarse al servidor.</span><span class="sxs-lookup"><span data-stu-id="22a3c-145">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="22a3c-146">Debe considerar el uso de un mecanismo de autenticación más seguro, por ejemplo, Kerberos o NT LAN Manager (NTLM). Si `defaultCredentials` es `true`, Kerberos o NTLM se utilizará si el servidor admite estos protocolos.</span><span class="sxs-lookup"><span data-stu-id="22a3c-146">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="22a3c-147">Las opciones de credenciales de red predeterminada y la autenticación básicas se excluyen mutuamente; Si establece `defaultCredentials` a `true` y especifique un nombre de usuario y una contraseña, se utiliza la credencial de red predeterminada y se omiten los datos de la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="22a3c-147">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="22a3c-148">Para la autenticación básica si especifica un `userName`, también debe especificar un `password` a la autenticación para el servidor de correo.</span><span class="sxs-lookup"><span data-stu-id="22a3c-148">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="22a3c-149">El <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> propiedad puede usarse para obtener el valor actual de la `userName` atributo desde archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="22a3c-149">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="22a3c-150">El <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> propiedad puede usarse para obtener el valor actual de la `password` atributo desde archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="22a3c-150">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="22a3c-151">Un `password` atributo no normalmente se especificaría en archivos de configuración por motivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="22a3c-151">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="22a3c-152">El `clientDomain` atributo cambia el nombre de dominio del cliente utilizado en la solicitud de protocolo SMTP inicial para un servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="22a3c-152">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="22a3c-153">El `clientDomain` atributo puede establecerse en el nombre de dominio completo del equipo local, en lugar de con el nombre de host local que se usa de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="22a3c-153">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="22a3c-154">Esto proporciona mayor compatibilidad con los estándares de protocolo SMTP.</span><span class="sxs-lookup"><span data-stu-id="22a3c-154">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="22a3c-155">El valor predeterminado es el nombre de host local del equipo local envía la solicitud.</span><span class="sxs-lookup"><span data-stu-id="22a3c-155">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="22a3c-156">El <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> propiedad puede usarse para obtener el valor actual de la `clientDomain` atributo desde archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="22a3c-156">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="22a3c-157">El `targetName` atributo se utiliza para la autenticación cuando se usa la protección extendida.</span><span class="sxs-lookup"><span data-stu-id="22a3c-157">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="22a3c-158">El valor predeterminado es el formato "SMTPSVC /\<host >" donde \<host > es el nombre de host del servidor de correo SMTP.</span><span class="sxs-lookup"><span data-stu-id="22a3c-158">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="22a3c-159">El <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> propiedad puede usarse para obtener el valor actual de la `targetName` atributo desde archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="22a3c-159">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="22a3c-160">El `enableSsl` atributo especifica si se usa SSL para tener acceso a un servidor de correo SMTP.</span><span class="sxs-lookup"><span data-stu-id="22a3c-160">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="22a3c-161">La <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> clase sólo admite la extensión de servicio SMTP para SMTP seguro a través de la seguridad de la capa de transporte como se define en RFC 3207.</span><span class="sxs-lookup"><span data-stu-id="22a3c-161">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="22a3c-162">En este modo, la sesión SMTP comienza en un canal no cifrado, a continuación, se emite un comando STARTTLS por el cliente al servidor para cambiar a una comunicación segura mediante SSL.</span><span class="sxs-lookup"><span data-stu-id="22a3c-162">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="22a3c-163">Vea RFC 3207 publicada por Internet Engineering Task Force (IETF) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="22a3c-163">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="22a3c-164">Un método de conexión alternativo es donde se establece por adelantado una sesión SSL antes de cualquier protocolo que se envían comandos.</span><span class="sxs-lookup"><span data-stu-id="22a3c-164">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="22a3c-165">Este método de conexión a veces se denomina SMTPS y usa el puerto 465 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="22a3c-165">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="22a3c-166">Este método de conexión alternativo mediante SSL no se admite actualmente.</span><span class="sxs-lookup"><span data-stu-id="22a3c-166">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="22a3c-167">El <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> propiedad puede usarse para obtener el valor actual de la `enableSsl` atributo desde archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="22a3c-167">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22a3c-168">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22a3c-168">Example</span></span>  
 <span data-ttu-id="22a3c-169">El ejemplo siguiente especifica los parámetros SMTP adecuados para enviar correo electrónico utilizando las credenciales de red predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="22a3c-169">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
        <network  
          clientDomain="www.contoso.com"  
          defaultCredentials="true"  
          enableSsl="false"  
          host="mail.contoso.com"  
          port="25"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="22a3c-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="22a3c-170">See also</span></span>

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [<span data-ttu-id="22a3c-171">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="22a3c-171">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
