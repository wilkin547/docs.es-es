---
title: '&lt;socket&gt; Element (Network Settings)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 995a89dd67664fd6a408f88f20f6837d2dbaaad4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744244"
---
# <a name="ltsocketgt-element-network-settings"></a><span data-ttu-id="8aac6-102">&lt;socket&gt; Element (Network Settings)</span><span class="sxs-lookup"><span data-stu-id="8aac6-102">&lt;socket&gt; Element (Network Settings)</span></span>
<span data-ttu-id="8aac6-103">Especifica si las operaciones de socket utilizan puertos de terminación.</span><span class="sxs-lookup"><span data-stu-id="8aac6-103">Specifies whether socket operations use completion ports.</span></span>  
  
 <span data-ttu-id="8aac6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8aac6-104">\<configuration></span></span>  
<span data-ttu-id="8aac6-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="8aac6-105">\<system.net></span></span>  
<span data-ttu-id="8aac6-106">\<Configuración ></span><span class="sxs-lookup"><span data-stu-id="8aac6-106">\<settings></span></span>  
<span data-ttu-id="8aac6-107">\<Socket ></span><span class="sxs-lookup"><span data-stu-id="8aac6-107">\<socket></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aac6-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8aac6-108">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8aac6-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8aac6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8aac6-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8aac6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8aac6-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="8aac6-111">Attributes</span></span>  
  
|<span data-ttu-id="8aac6-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="8aac6-112">**Attribute**</span></span>|<span data-ttu-id="8aac6-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8aac6-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="8aac6-114">Indica si el socket siempre debería utilizar los puertos de terminación para llamadas al método Accept.</span><span class="sxs-lookup"><span data-stu-id="8aac6-114">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="8aac6-115">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="8aac6-115">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="8aac6-116">Indica si el socket siempre debería utilizar los puertos de terminación para llamadas al método Connect.</span><span class="sxs-lookup"><span data-stu-id="8aac6-116">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="8aac6-117">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="8aac6-117">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="8aac6-118">Especifica el valor predeterminado <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> debe utilizar para un socket.</span><span class="sxs-lookup"><span data-stu-id="8aac6-118">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="8aac6-119">El valor predeterminado depende de la versión de Windows.</span><span class="sxs-lookup"><span data-stu-id="8aac6-119">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8aac6-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8aac6-120">Child Elements</span></span>  
 <span data-ttu-id="8aac6-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8aac6-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8aac6-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8aac6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8aac6-123">**Element**</span><span class="sxs-lookup"><span data-stu-id="8aac6-123">**Element**</span></span>|<span data-ttu-id="8aac6-124">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8aac6-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8aac6-125">Configuración</span><span class="sxs-lookup"><span data-stu-id="8aac6-125">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="8aac6-126">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="8aac6-126">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8aac6-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8aac6-127">Remarks</span></span>  
 <span data-ttu-id="8aac6-128">El `alwaysUseCompletionPortsForAccept` y `alwaysUseCompletionPortsForConnect` atributos se usan para especificar el comportamiento predeterminado con respecto al uso de puertos de terminación de las clases en el <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span><span class="sxs-lookup"><span data-stu-id="8aac6-128">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="8aac6-129">Los puertos de terminación se recomiendan para aplicaciones de servidor de alto rendimiento.</span><span class="sxs-lookup"><span data-stu-id="8aac6-129">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="8aac6-130">El valor predeterminado para la `alwaysUseCompletionPortsForAccept` y `alwaysUseCompletionPortsForConnect` atributos **false**.</span><span class="sxs-lookup"><span data-stu-id="8aac6-130">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="8aac6-131">El <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> puede utilizarse para obtener el valor actual de la `alwaysUseCompletionPortsForAccept` atributos de archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="8aac6-131">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="8aac6-132">El <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> puede utilizarse para obtener el valor actual de la `alwaysUseCompletionPortsForConnect` atributos de archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="8aac6-132">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="8aac6-133">El `ipProtectionLevel` atributo especifica el valor predeterminado <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> debe utilizar para un socket.</span><span class="sxs-lookup"><span data-stu-id="8aac6-133">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="8aac6-134">El <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> propiedad permite la configuración de una restricción para un socket IPv6 a un ámbito especificado, como direcciones con el mismo vínculo locales o prefijo local del sitio.</span><span class="sxs-lookup"><span data-stu-id="8aac6-134">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="8aac6-135">Esta opción permite a las aplicaciones colocar restricciones de acceso en sockets IPv6.</span><span class="sxs-lookup"><span data-stu-id="8aac6-135">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="8aac6-136">Estas restricciones permiten que una aplicación que se ejecuta en una LAN privada se fortalezca de forma sencilla frente a ataques externos.</span><span class="sxs-lookup"><span data-stu-id="8aac6-136">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="8aac6-137">Esta opción amplía o reduce el ámbito de un socket de escucha, lo que permite el acceso no restringido de usuarios públicos y privados cuando sea adecuado o restringe el acceso únicamente al mismo sitio, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="8aac6-137">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="8aac6-138">Esto `ipProtectionLevel` afecta a la configuración del atributo solamente el tráfico entrante inicial:</span><span class="sxs-lookup"><span data-stu-id="8aac6-138">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
-   <span data-ttu-id="8aac6-139">Un servidor TCP escuchar las conexiones entrantes en un socket.</span><span class="sxs-lookup"><span data-stu-id="8aac6-139">A TCP server listening for incoming connections on a socket.</span></span>  
  
-   <span data-ttu-id="8aac6-140">Una aplicación de UDP recibir un paquete en un socket.</span><span class="sxs-lookup"><span data-stu-id="8aac6-140">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="8aac6-141">Esta opción de configuración no afecta a las conexiones TCP ya se ha establecido (tráfico no tiene restricciones en ambas direcciones) y no afecta a ninguna aplicación que envíe paquetes UDP.</span><span class="sxs-lookup"><span data-stu-id="8aac6-141">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="8aac6-142">Los valores posibles de la `ipProtectionLevel` configuración del atributo se corresponden con los niveles de protección definidos especificados en la <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeración como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="8aac6-142">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|<span data-ttu-id="8aac6-143">**Valor de atributo**</span><span class="sxs-lookup"><span data-stu-id="8aac6-143">**Attribute Value**</span></span>|<span data-ttu-id="8aac6-144">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8aac6-144">**Description**</span></span>|  
|-|-|  
|<span data-ttu-id="8aac6-145">EdgeRestricted</span><span class="sxs-lookup"><span data-stu-id="8aac6-145">EdgeRestricted</span></span>|<span data-ttu-id="8aac6-146">El nivel de protección de IP tiene una restricción perimetral.</span><span class="sxs-lookup"><span data-stu-id="8aac6-146">The IP protection level is edge restricted.</span></span> <span data-ttu-id="8aac6-147">Este valor se usaría por aplicaciones diseñadas para funcionar a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="8aac6-147">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="8aac6-148">Esta configuración no permitir cruce seguro de traducción de direcciones de red (NAT) mediante la implementación de Windows Teredo.</span><span class="sxs-lookup"><span data-stu-id="8aac6-148">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="8aac6-149">Estas aplicaciones pueden eludir los firewalls de IPv4, por lo que se deben reforzar las aplicaciones frente a ataques de Internet que se dirigen al puerto abierto.</span><span class="sxs-lookup"><span data-stu-id="8aac6-149">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="8aac6-150">En Windows Server 2003 y Windows XP, el valor predeterminado para el nivel de protección de IP en un socket es borde restringido.</span><span class="sxs-lookup"><span data-stu-id="8aac6-150">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="8aac6-151">Restringido</span><span class="sxs-lookup"><span data-stu-id="8aac6-151">Restricted</span></span>|<span data-ttu-id="8aac6-152">El nivel de protección de IP está restringido.</span><span class="sxs-lookup"><span data-stu-id="8aac6-152">The IP protection level is restricted.</span></span> <span data-ttu-id="8aac6-153">Este valor se usaría las aplicaciones de intranet que no implementan escenarios de Internet.</span><span class="sxs-lookup"><span data-stu-id="8aac6-153">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="8aac6-154">Estas aplicaciones son generalmente no probadas o protege frente a ataques de estilo de Internet.</span><span class="sxs-lookup"><span data-stu-id="8aac6-154">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="8aac6-155">Esta opción limitará el tráfico recibido a las direcciones locales de vínculo.</span><span class="sxs-lookup"><span data-stu-id="8aac6-155">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="8aac6-156">Sin restricción</span><span class="sxs-lookup"><span data-stu-id="8aac6-156">Unrestricted</span></span>|<span data-ttu-id="8aac6-157">El nivel de protección de IP no está restringido.</span><span class="sxs-lookup"><span data-stu-id="8aac6-157">The IP protection level is unrestricted.</span></span> <span data-ttu-id="8aac6-158">Este valor se usaría por aplicaciones diseñadas para funcionar a través de Internet, incluidas las aplicaciones de sacar partido de las funciones de cruce seguro de NAT de IPv6 integradas en Windows (por ejemplo, Teredo).</span><span class="sxs-lookup"><span data-stu-id="8aac6-158">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="8aac6-159">Estas aplicaciones pueden eludir los firewalls de IPv4, por lo que se deben reforzar las aplicaciones frente a ataques de Internet que se dirigen al puerto abierto.</span><span class="sxs-lookup"><span data-stu-id="8aac6-159">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="8aac6-160">En Windows Server 2008 R2 y Windows Vista, el valor predeterminado para el nivel de protección de IP en un socket no está restringido.</span><span class="sxs-lookup"><span data-stu-id="8aac6-160">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="8aac6-161">Sin especificar</span><span class="sxs-lookup"><span data-stu-id="8aac6-161">Unspecified</span></span>|<span data-ttu-id="8aac6-162">El nivel de protección de IP no está especificado.</span><span class="sxs-lookup"><span data-stu-id="8aac6-162">The IP protection level is unspecified.</span></span> <span data-ttu-id="8aac6-163">En Windows 7 y Windows Server 2008 R2, el valor predeterminado para el nivel de protección de IP en un socket no está especificado.</span><span class="sxs-lookup"><span data-stu-id="8aac6-163">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="8aac6-164">El valor predeterminado para la `ipProtectionLevel` atributo es **Unspecified**.</span><span class="sxs-lookup"><span data-stu-id="8aac6-164">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="8aac6-165">El <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> propiedad puede utilizarse para obtener el valor actual de la `ipProtectionLevel` atributos de archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="8aac6-165">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8aac6-166">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="8aac6-166">Configuration Files</span></span>  
 <span data-ttu-id="8aac6-167">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="8aac6-167">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8aac6-168">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8aac6-168">Example</span></span>  
 <span data-ttu-id="8aac6-169">En el ejemplo siguiente se muestra cómo especificar que se deben usar los puertos de terminación y que el valor predeterminado <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> debe ser sin restricciones.</span><span class="sxs-lookup"><span data-stu-id="8aac6-169">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <socket  
        alwaysUseCompletionPortsForAccept="true"  
        alwaysUseCompletionPortsForConnect="true"  
        ipProtectionLevel="Unrestricted"  
       />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8aac6-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="8aac6-170">See Also</span></span>  
 <xref:System.Net?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>  
 <xref:System.Net.Sockets?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>  
 [<span data-ttu-id="8aac6-171">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="8aac6-171">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
