---
title: Elemento <network> (configuración de red)
description: El <network> elemento configuración de red configura las opciones de red para una opción de servidor SMTP externo en el .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: cd142febc0b3aacf1be7978178a6a05d9b9aebbf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190285"
---
# <a name="network-element-network-settings"></a><span data-ttu-id="6fabd-103">Elemento \<network> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="6fabd-103">\<network> Element (Network Settings)</span></span>

<span data-ttu-id="6fabd-104">Configura las opciones de red para un servidor de Protocolo simple de transferencia de correo (SMTP) externo.</span><span class="sxs-lookup"><span data-stu-id="6fabd-104">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<network>**

## <a name="syntax"></a><span data-ttu-id="6fabd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6fabd-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6fabd-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6fabd-106">Attributes and Elements</span></span>  

 <span data-ttu-id="6fabd-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6fabd-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6fabd-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="6fabd-108">Attributes</span></span>  
  
|<span data-ttu-id="6fabd-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="6fabd-109">Attribute</span></span>|<span data-ttu-id="6fabd-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="6fabd-110">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="6fabd-111">Especifica el nombre de dominio de cliente que se va a usar en la solicitud de protocolo SMTP inicial para conectarse al servidor de correo SMTP.</span><span class="sxs-lookup"><span data-stu-id="6fabd-111">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="6fabd-112">El valor predeterminado es el nombre localhost del equipo local que envía la solicitud.</span><span class="sxs-lookup"><span data-stu-id="6fabd-112">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="6fabd-113">Especifica si se deben usar las credenciales de usuario predeterminadas para obtener acceso al servidor de correo SMTP para las transacciones SMTP.</span><span class="sxs-lookup"><span data-stu-id="6fabd-113">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="6fabd-114">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="6fabd-114">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="6fabd-115">Especifica si se utiliza SSL para tener acceso a un servidor de correo SMTP.</span><span class="sxs-lookup"><span data-stu-id="6fabd-115">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="6fabd-116">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="6fabd-116">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="6fabd-117">Especifica el nombre de host del servidor de correo SMTP que se va a usar para las transacciones SMTP.</span><span class="sxs-lookup"><span data-stu-id="6fabd-117">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="6fabd-118">Este atributo no tiene ningún valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6fabd-118">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="6fabd-119">Especifica la contraseña que se utilizará para la autenticación en el servidor de correo SMTP.</span><span class="sxs-lookup"><span data-stu-id="6fabd-119">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="6fabd-120">Este atributo no tiene ningún valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6fabd-120">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="6fabd-121">Especifica el número de puerto que se va a utilizar para conectarse al servidor de correo SMTP.</span><span class="sxs-lookup"><span data-stu-id="6fabd-121">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="6fabd-122">El valor predeterminado es 25.</span><span class="sxs-lookup"><span data-stu-id="6fabd-122">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="6fabd-123">Especifica el nombre del proveedor de servicios (SPN) que se va a usar para la autenticación cuando se usa la protección extendida para transacciones SMTP.</span><span class="sxs-lookup"><span data-stu-id="6fabd-123">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="6fabd-124">Este atributo no tiene ningún valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6fabd-124">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="6fabd-125">Especifica el nombre de usuario que se utilizará para la autenticación en el servidor de correo SMTP.</span><span class="sxs-lookup"><span data-stu-id="6fabd-125">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="6fabd-126">Este atributo no tiene ningún valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6fabd-126">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6fabd-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6fabd-127">Child Elements</span></span>  

 <span data-ttu-id="6fabd-128">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6fabd-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6fabd-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6fabd-129">Parent Elements</span></span>  
  
|<span data-ttu-id="6fabd-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="6fabd-130">Element</span></span>|<span data-ttu-id="6fabd-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="6fabd-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6fabd-132">Elemento \<smtp> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="6fabd-132">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="6fabd-133">Configura las opciones de envío de correo del Protocolo simple de transferencia de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="6fabd-133">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6fabd-134">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6fabd-134">Remarks</span></span>  

 <span data-ttu-id="6fabd-135">Algunos servidores SMTP requieren que se autentique en el servidor antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="6fabd-135">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="6fabd-136">Si desea autenticarse con las credenciales de red predeterminadas en el host, establezca el `defaultCredentials` atributo en `true` .</span><span class="sxs-lookup"><span data-stu-id="6fabd-136">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="6fabd-137">La <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> propiedad se puede utilizar para obtener el valor actual del `defaultCredentials` atributo desde los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="6fabd-137">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="6fabd-138">También puede usar la autenticación básica (un nombre de usuario y una contraseña) para autenticarse en el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="6fabd-138">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="6fabd-139">Para usar esta opción, debe especificar un nombre de usuario y una contraseña válidos para el servidor SMTP especificado.</span><span class="sxs-lookup"><span data-stu-id="6fabd-139">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6fabd-140">La autenticación básica envía `userName` los `password` valores y al servidor sin cifrar.</span><span class="sxs-lookup"><span data-stu-id="6fabd-140">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="6fabd-141">Cualquier persona que supervise el tráfico de red puede ver sus credenciales y usarlas para conectarse al servidor.</span><span class="sxs-lookup"><span data-stu-id="6fabd-141">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="6fabd-142">Considere la posibilidad de usar un mecanismo de autenticación más seguro, como Kerberos o NT LAN Manager (NTLM). Si `defaultCredentials` es `true` , se utilizará Kerberos o NTLM si el servidor admite estos protocolos.</span><span class="sxs-lookup"><span data-stu-id="6fabd-142">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="6fabd-143">Las opciones de autenticación básica y de credenciales de red predeterminadas son mutuamente excluyentes; Si establece `defaultCredentials` en `true` y especifica un nombre de usuario y una contraseña, se usa la credencial de red predeterminada y se omiten los datos de autenticación básicos.</span><span class="sxs-lookup"><span data-stu-id="6fabd-143">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="6fabd-144">En el caso de la autenticación básica `userName` , si especifica, debe especificar también un `password` para la autenticación en el servidor de correo.</span><span class="sxs-lookup"><span data-stu-id="6fabd-144">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="6fabd-145">La <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> propiedad se puede utilizar para obtener el valor actual del `userName` atributo desde los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="6fabd-145">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="6fabd-146">La <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> propiedad se puede utilizar para obtener el valor actual del `password` atributo desde los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="6fabd-146">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="6fabd-147">Normalmente, un `password` atributo no se escribiría en los archivos de configuración por motivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6fabd-147">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="6fabd-148">El `clientDomain` atributo cambia el nombre de dominio del cliente utilizado en la solicitud de protocolo SMTP inicial a un servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="6fabd-148">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="6fabd-149">El `clientDomain` atributo se puede establecer en el nombre de dominio completo del equipo local, en lugar del nombre de host local que se utiliza de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6fabd-149">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="6fabd-150">Esto proporciona mayor compatibilidad con los estándares de protocolo SMTP.</span><span class="sxs-lookup"><span data-stu-id="6fabd-150">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="6fabd-151">El valor predeterminado es el nombre localhost del equipo local que envía la solicitud.</span><span class="sxs-lookup"><span data-stu-id="6fabd-151">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="6fabd-152">La <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> propiedad se puede utilizar para obtener el valor actual del `clientDomain` atributo desde los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="6fabd-152">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="6fabd-153">El `targetName` atributo se utiliza para la autenticación cuando se usa la protección ampliada.</span><span class="sxs-lookup"><span data-stu-id="6fabd-153">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="6fabd-154">El valor predeterminado tiene el formato "SMTPSVC/ \<host> ", donde \<host> es el nombre de host del servidor de correo SMTP.</span><span class="sxs-lookup"><span data-stu-id="6fabd-154">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="6fabd-155">La <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> propiedad se puede utilizar para obtener el valor actual del `targetName` atributo desde los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="6fabd-155">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="6fabd-156">El `enableSsl` atributo especifica si se utiliza SSL para tener acceso a un servidor de correo SMTP.</span><span class="sxs-lookup"><span data-stu-id="6fabd-156">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="6fabd-157">La <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> clase solo admite la extensión de servicio SMTP para SMTP seguro a través de la seguridad de la capa de transporte, tal y como se define en RFC 3207.</span><span class="sxs-lookup"><span data-stu-id="6fabd-157">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="6fabd-158">En este modo, la sesión SMTP se inicia en un canal sin cifrar y, a continuación, el cliente emite un comando STARTTLS al servidor para cambiar a la comunicación segura mediante SSL.</span><span class="sxs-lookup"><span data-stu-id="6fabd-158">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="6fabd-159">Para obtener más información, consulte RFC 3207 publicado por el equipo de ingeniería de Internet (IETF).</span><span class="sxs-lookup"><span data-stu-id="6fabd-159">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="6fabd-160">Un método de conexión alternativo es el lugar en el que se establece una sesión SSL antes de que se envíen los comandos del protocolo.</span><span class="sxs-lookup"><span data-stu-id="6fabd-160">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="6fabd-161">Este método de conexión se denomina a veces SMTP y, de forma predeterminada, usa el puerto 465.</span><span class="sxs-lookup"><span data-stu-id="6fabd-161">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="6fabd-162">Este método de conexión alternativo que usa SSL no se admite actualmente.</span><span class="sxs-lookup"><span data-stu-id="6fabd-162">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="6fabd-163">La <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> propiedad se puede utilizar para obtener el valor actual del `enableSsl` atributo desde los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="6fabd-163">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fabd-164">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6fabd-164">Example</span></span>  

 <span data-ttu-id="6fabd-165">En el ejemplo siguiente se especifican los parámetros SMTP adecuados para enviar correo electrónico con las credenciales de red predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="6fabd-165">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6fabd-166">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6fabd-166">See also</span></span>

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [<span data-ttu-id="6fabd-167">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="6fabd-167">Network Settings Schema</span></span>](index.md)
