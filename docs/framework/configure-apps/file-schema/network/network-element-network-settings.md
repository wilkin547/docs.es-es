---
title: Elemento <network> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: f7cfcc3b9d5a717c23175cd15aa48ae97c828e57
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154821"
---
# <a name="network-element-network-settings"></a><span data-ttu-id="93b4a-102">\<Elemento> de red (Configuración de red)</span><span class="sxs-lookup"><span data-stu-id="93b4a-102">\<network> Element (Network Settings)</span></span>
<span data-ttu-id="93b4a-103">Configura las opciones de red para un servidor de Protocolo simple de transporte de correo (SMTP) externo.</span><span class="sxs-lookup"><span data-stu-id="93b4a-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  

<span data-ttu-id="93b4a-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="93b4a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="93b4a-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="93b4a-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="93b4a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="93b4a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>\
<span data-ttu-id="93b4a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>smtp**](smtp-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="93b4a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>\
<span data-ttu-id="93b4a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>de red**</span><span class="sxs-lookup"><span data-stu-id="93b4a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<network>**</span></span>

## <a name="syntax"></a><span data-ttu-id="93b4a-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93b4a-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93b4a-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="93b4a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="93b4a-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="93b4a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93b4a-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="93b4a-112">Attributes</span></span>  
  
|<span data-ttu-id="93b4a-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="93b4a-113">Attribute</span></span>|<span data-ttu-id="93b4a-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="93b4a-114">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="93b4a-115">Especifica el nombre de dominio de cliente que se usará en la solicitud de protocolo SMTP inicial para conectarse al servidor de correo SMTP.</span><span class="sxs-lookup"><span data-stu-id="93b4a-115">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="93b4a-116">El valor predeterminado es el nombre de host local del equipo local que envía la solicitud.</span><span class="sxs-lookup"><span data-stu-id="93b4a-116">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="93b4a-117">Especifica si se deben usar las credenciales de usuario predeterminadas para acceder al servidor de correo SMTP para las transacciones SMTP.</span><span class="sxs-lookup"><span data-stu-id="93b4a-117">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="93b4a-118">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="93b4a-118">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="93b4a-119">Especifica si se utiliza SSL para acceder a un servidor de correo SMTP.</span><span class="sxs-lookup"><span data-stu-id="93b4a-119">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="93b4a-120">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="93b4a-120">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="93b4a-121">Especifica el nombre de host del servidor de correo SMTP que se usará para las transacciones SMTP.</span><span class="sxs-lookup"><span data-stu-id="93b4a-121">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="93b4a-122">Este atributo no tiene ningún valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="93b4a-122">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="93b4a-123">Especifica la contraseña que se usará para la autenticación en el servidor de correo SMTP.</span><span class="sxs-lookup"><span data-stu-id="93b4a-123">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="93b4a-124">Este atributo no tiene ningún valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="93b4a-124">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="93b4a-125">Especifica el número de puerto que se utilizará para conectarse al servidor de correo SMTP.</span><span class="sxs-lookup"><span data-stu-id="93b4a-125">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="93b4a-126">El valor predeterminado es 25.</span><span class="sxs-lookup"><span data-stu-id="93b4a-126">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="93b4a-127">Especifica el nombre del proveedor de servicios (SPN) que se usará para la autenticación cuando se usa protección ampliada para transacciones SMTP.</span><span class="sxs-lookup"><span data-stu-id="93b4a-127">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="93b4a-128">Este atributo no tiene ningún valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="93b4a-128">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="93b4a-129">Especifica el nombre de usuario que se usará para la autenticación en el servidor de correo SMTP.</span><span class="sxs-lookup"><span data-stu-id="93b4a-129">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="93b4a-130">Este atributo no tiene ningún valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="93b4a-130">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93b4a-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="93b4a-131">Child Elements</span></span>  
 <span data-ttu-id="93b4a-132">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="93b4a-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93b4a-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="93b4a-133">Parent Elements</span></span>  
  
|<span data-ttu-id="93b4a-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="93b4a-134">Element</span></span>|<span data-ttu-id="93b4a-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="93b4a-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93b4a-136">\<Elemento> smtp (Configuración de red)</span><span class="sxs-lookup"><span data-stu-id="93b4a-136">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="93b4a-137">Configura las opciones de envío de correo del Protocolo simple de transporte de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="93b4a-137">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93b4a-138">Observaciones</span><span class="sxs-lookup"><span data-stu-id="93b4a-138">Remarks</span></span>  
 <span data-ttu-id="93b4a-139">Algunos servidores SMTP requieren que se autentique en el servidor antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="93b4a-139">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="93b4a-140">Si desea autenticarse con las credenciales de red `defaultCredentials` predeterminadas `true`en el host, establezca el atributo en .</span><span class="sxs-lookup"><span data-stu-id="93b4a-140">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="93b4a-141">La <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> propiedad se puede utilizar para `defaultCredentials` obtener el valor actual del atributo de los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="93b4a-141">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="93b4a-142">También puede utilizar la autenticación básica (un nombre de usuario y una contraseña) para autenticarse en el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="93b4a-142">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="93b4a-143">Para utilizar esta opción, debe especificar un nombre de usuario y una contraseña válidos para el servidor SMTP especificado.</span><span class="sxs-lookup"><span data-stu-id="93b4a-143">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="93b4a-144">La autenticación `userName` básica `password` envía los valores y al servidor sin cifrar.</span><span class="sxs-lookup"><span data-stu-id="93b4a-144">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="93b4a-145">Cualquier persona que supervise el tráfico de red puede ver sus credenciales y usarlas para conectarse al servidor.</span><span class="sxs-lookup"><span data-stu-id="93b4a-145">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="93b4a-146">Debe considerar el uso de un mecanismo de autenticación más seguro, como Kerberos o NT LAN Manager (NTLM.) Si `defaultCredentials` `true`es , se utilizará Kerberos o NTLM si el servidor admite estos protocolos.</span><span class="sxs-lookup"><span data-stu-id="93b4a-146">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="93b4a-147">Las opciones básicas de autenticación y credenciales de red predeterminadas son mutuamente excluyentes; si establece `defaultCredentials` `true` y especifica un nombre de usuario y una contraseña, se utiliza la credencial de red predeterminada y se omiten los datos de autenticación básicos.</span><span class="sxs-lookup"><span data-stu-id="93b4a-147">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="93b4a-148">Para la autenticación básica `userName`si especifica un `password` , también debe especificar a para la autenticación usted mismo para el servidor de correo.</span><span class="sxs-lookup"><span data-stu-id="93b4a-148">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="93b4a-149">La <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> propiedad se puede utilizar para `userName` obtener el valor actual del atributo de los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="93b4a-149">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="93b4a-150">La <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> propiedad se puede utilizar para `password` obtener el valor actual del atributo de los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="93b4a-150">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="93b4a-151">Normalmente, `password` no se introduciría un atributo en los archivos de configuración por motivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="93b4a-151">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="93b4a-152">El `clientDomain` atributo cambia el nombre de dominio de cliente utilizado en la solicitud de protocolo SMTP inicial a un servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="93b4a-152">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="93b4a-153">El `clientDomain` atributo se puede establecer en el nombre de dominio completo de la máquina local, en lugar del nombre de host local que se usa de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="93b4a-153">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="93b4a-154">Esto proporciona un mayor cumplimiento con los estándares de protocolo SMTP.</span><span class="sxs-lookup"><span data-stu-id="93b4a-154">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="93b4a-155">El valor predeterminado es el nombre de host local del equipo local que envía la solicitud.</span><span class="sxs-lookup"><span data-stu-id="93b4a-155">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="93b4a-156">La <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> propiedad se puede utilizar para `clientDomain` obtener el valor actual del atributo de los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="93b4a-156">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="93b4a-157">El `targetName` atributo se utiliza para la autenticación cuando se usa la protección extendida.</span><span class="sxs-lookup"><span data-stu-id="93b4a-157">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="93b4a-158">El valor predeterminado es del formulario\<"SMTPSVC/ host>" donde \<el host> es el nombre de host del servidor de correo SMTP.</span><span class="sxs-lookup"><span data-stu-id="93b4a-158">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="93b4a-159">La <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> propiedad se puede utilizar para `targetName` obtener el valor actual del atributo de los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="93b4a-159">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="93b4a-160">El `enableSsl` atributo especifica si SSL se utiliza para acceder a un servidor de correo SMTP.</span><span class="sxs-lookup"><span data-stu-id="93b4a-160">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="93b4a-161">La <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> clase solo admite la extensión de servicio SMTP para SMTP seguro sobre la seguridad de la capa de transporte tal como se define en RFC 3207.</span><span class="sxs-lookup"><span data-stu-id="93b4a-161">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="93b4a-162">En este modo, la sesión SMTP comienza en un canal sin cifrar y, a continuación, el cliente emite un comando STARTTLS al servidor para cambiar a la comunicación segura mediante SSL.</span><span class="sxs-lookup"><span data-stu-id="93b4a-162">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="93b4a-163">Consulte RFC 3207 publicado por internet Engineering Task Force (IETF) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="93b4a-163">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="93b4a-164">Un método de conexión alternativo es donde se establece una sesión SSL por adelantado antes de enviar los comandos de protocolo.</span><span class="sxs-lookup"><span data-stu-id="93b4a-164">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="93b4a-165">Este método de conexión a veces se denomina SMTPS y, de forma predeterminada, utiliza el puerto 465.</span><span class="sxs-lookup"><span data-stu-id="93b4a-165">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="93b4a-166">Actualmente no se admite este método de conexión alternativo mediante SSL.</span><span class="sxs-lookup"><span data-stu-id="93b4a-166">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="93b4a-167">La <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> propiedad se puede utilizar para `enableSsl` obtener el valor actual del atributo de los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="93b4a-167">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93b4a-168">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="93b4a-168">Example</span></span>  
 <span data-ttu-id="93b4a-169">En el ejemplo siguiente se especifican los parámetros SMTP adecuados para enviar correo electrónico con las credenciales de red predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="93b4a-169">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="93b4a-170">Consulte también</span><span class="sxs-lookup"><span data-stu-id="93b4a-170">See also</span></span>

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [<span data-ttu-id="93b4a-171">Esquema de configuración de red</span><span class="sxs-lookup"><span data-stu-id="93b4a-171">Network Settings Schema</span></span>](index.md)
