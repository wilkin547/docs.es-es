---
title: <socket> Elemento (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
ms.openlocfilehash: 82bfe3b6e3107ff787716657dbf0b31dcadde911
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160165"
---
# <a name="socket-element-network-settings"></a><span data-ttu-id="e3b6e-102">\<Socket > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="e3b6e-102">\<socket> Element (Network Settings)</span></span>
<span data-ttu-id="e3b6e-103">Especifica si las operaciones de socket utilizan puertos de terminación.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-103">Specifies whether socket operations use completion ports.</span></span>  
  
 <span data-ttu-id="e3b6e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e3b6e-104">\<configuration></span></span>  
<span data-ttu-id="e3b6e-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="e3b6e-105">\<system.net></span></span>  
<span data-ttu-id="e3b6e-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="e3b6e-106">\<settings></span></span>  
<span data-ttu-id="e3b6e-107">\<Socket ></span><span class="sxs-lookup"><span data-stu-id="e3b6e-107">\<socket></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3b6e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3b6e-108">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3b6e-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e3b6e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e3b6e-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3b6e-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="e3b6e-111">Attributes</span></span>  
  
|**<span data-ttu-id="e3b6e-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="e3b6e-112">Attribute</span></span>**|**<span data-ttu-id="e3b6e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3b6e-113">Description</span></span>**|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="e3b6e-114">Indica si el socket siempre debería utilizar los puertos de terminación para llamadas al método de aceptación.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-114">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="e3b6e-115">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-115">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="e3b6e-116">Indica si el socket siempre debería utilizar los puertos de terminación para llamadas al método Connect.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-116">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="e3b6e-117">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-117">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="e3b6e-118">Especifica el valor predeterminado <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> a utilizar para un socket.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-118">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="e3b6e-119">El valor predeterminado depende de la versión de Windows.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-119">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e3b6e-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e3b6e-120">Child Elements</span></span>  
 <span data-ttu-id="e3b6e-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e3b6e-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e3b6e-122">Parent Elements</span></span>  
  
|**<span data-ttu-id="e3b6e-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="e3b6e-123">Element</span></span>**|**<span data-ttu-id="e3b6e-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3b6e-124">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="e3b6e-125">configuración</span><span class="sxs-lookup"><span data-stu-id="e3b6e-125">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="e3b6e-126">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-126">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3b6e-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e3b6e-127">Remarks</span></span>  
 <span data-ttu-id="e3b6e-128">El `alwaysUseCompletionPortsForAccept` y `alwaysUseCompletionPortsForConnect` atributos se usan para especificar el comportamiento predeterminado con respecto al uso de puertos de terminación de las clases en el <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-128">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="e3b6e-129">Se recomiendan los puertos de finalización para las aplicaciones de servidor de alto rendimiento.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-129">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="e3b6e-130">El valor predeterminado para el `alwaysUseCompletionPortsForAccept` y `alwaysUseCompletionPortsForConnect` atributos **false**.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-130">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="e3b6e-131">El <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> puede usarse para obtener el valor actual de la `alwaysUseCompletionPortsForAccept` atributo desde archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-131">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="e3b6e-132">El <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> puede usarse para obtener el valor actual de la `alwaysUseCompletionPortsForConnect` atributo desde archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-132">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="e3b6e-133">El `ipProtectionLevel` atributo especifica el valor predeterminado <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> a utilizar para un socket.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-133">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="e3b6e-134">El <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> propiedad habilita la configuración de una restricción para un socket IPv6 a un ámbito especificado, como direcciones con el mismo vínculo o sitio prefijo local.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-134">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="e3b6e-135">Esta opción permite a las aplicaciones colocar restricciones de acceso en sockets IPv6.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-135">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="e3b6e-136">Estas restricciones permiten que una aplicación que se ejecuta en una LAN privada se fortalezca de forma sencilla frente a ataques externos.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-136">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="e3b6e-137">Esta opción se amplía o reduce el ámbito de un socket de escucha, permite el acceso no restringido de usuarios públicos y privados cuando sea adecuado o restringir el acceso únicamente al mismo sitio, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-137">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="e3b6e-138">Esto `ipProtectionLevel` sólo tráfico inicial entrante afecta a la configuración del atributo:</span><span class="sxs-lookup"><span data-stu-id="e3b6e-138">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
-   <span data-ttu-id="e3b6e-139">Un servidor de TCP escucha las conexiones entrantes en un socket.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-139">A TCP server listening for incoming connections on a socket.</span></span>  
  
-   <span data-ttu-id="e3b6e-140">Una aplicación de UDP recibir un paquete en un socket.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-140">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="e3b6e-141">Esta opción de configuración no afecta a las conexiones ya se ha establecido de TCP (tráfico no tiene restricciones en ambas direcciones) y no afecta a una aplicación que envía paquetes UDP.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-141">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="e3b6e-142">Los valores posibles de la `ipProtectionLevel` configuración del atributo se corresponden con los niveles de protección especificados en la <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeración como sigue:</span><span class="sxs-lookup"><span data-stu-id="e3b6e-142">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|**<span data-ttu-id="e3b6e-143">Valor del atributo</span><span class="sxs-lookup"><span data-stu-id="e3b6e-143">Attribute Value</span></span>**|**<span data-ttu-id="e3b6e-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3b6e-144">Description</span></span>**|  
|-|-|  
|<span data-ttu-id="e3b6e-145">EdgeRestricted</span><span class="sxs-lookup"><span data-stu-id="e3b6e-145">EdgeRestricted</span></span>|<span data-ttu-id="e3b6e-146">El nivel de protección de IP tiene una restricción perimetral.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-146">The IP protection level is edge restricted.</span></span> <span data-ttu-id="e3b6e-147">Este valor lo usan las aplicaciones diseñadas para funcionar a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-147">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="e3b6e-148">Esta configuración no permite la exploración transversal de traducción de direcciones de red (NAT) mediante la implementación de Teredo de Windows.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-148">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="e3b6e-149">Estas aplicaciones pueden eludir los firewalls de IPv4, por lo que las aplicaciones deben protegerse frente a ataques de Internet dirigidos al puerto abierto.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-149">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="e3b6e-150">En Windows Server 2003 y Windows XP, el valor predeterminado para el nivel de protección de IP en un socket es la restricción perimetral.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-150">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="e3b6e-151">Restringido</span><span class="sxs-lookup"><span data-stu-id="e3b6e-151">Restricted</span></span>|<span data-ttu-id="e3b6e-152">El nivel de protección de IP está restringido.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-152">The IP protection level is restricted.</span></span> <span data-ttu-id="e3b6e-153">Este valor lo usan las aplicaciones de intranet que no implementan escenarios de Internet.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-153">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="e3b6e-154">Estas aplicaciones son por lo general no probadas o protegidas contra ataques por Internet.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-154">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="e3b6e-155">Este valor limitará el tráfico recibido a las direcciones locales de vínculo.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-155">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="e3b6e-156">Sin restricción</span><span class="sxs-lookup"><span data-stu-id="e3b6e-156">Unrestricted</span></span>|<span data-ttu-id="e3b6e-157">El nivel de protección IP no está restringido.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-157">The IP protection level is unrestricted.</span></span> <span data-ttu-id="e3b6e-158">Este valor lo usan las aplicaciones diseñadas para funcionar a través de Internet, incluidas las aplicaciones aprovechar las capacidades de cruce seguro de NAT de IPv6 integradas en Windows (por ejemplo, Teredo).</span><span class="sxs-lookup"><span data-stu-id="e3b6e-158">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="e3b6e-159">Estas aplicaciones pueden eludir los firewalls de IPv4, por lo que las aplicaciones deben protegerse frente a ataques de Internet dirigidos al puerto abierto.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-159">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="e3b6e-160">En Windows Server 2008 R2 y Windows Vista, el valor predeterminado para el nivel de protección de IP en un socket no está restringido.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-160">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="e3b6e-161">Sin especificar</span><span class="sxs-lookup"><span data-stu-id="e3b6e-161">Unspecified</span></span>|<span data-ttu-id="e3b6e-162">El nivel de protección IP no está especificado.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-162">The IP protection level is unspecified.</span></span> <span data-ttu-id="e3b6e-163">En Windows 7 y Windows Server 2008 R2, el valor predeterminado para el nivel de protección de IP en un socket no está especificado.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-163">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="e3b6e-164">El valor predeterminado para el `ipProtectionLevel` atributo es **Unspecified**.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-164">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="e3b6e-165">El <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> propiedad puede usarse para obtener el valor actual de la `ipProtectionLevel` atributo desde archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-165">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e3b6e-166">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="e3b6e-166">Configuration Files</span></span>  
 <span data-ttu-id="e3b6e-167">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e3b6e-167">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3b6e-168">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e3b6e-168">Example</span></span>  
 <span data-ttu-id="e3b6e-169">El ejemplo siguiente muestra cómo especificar que se deben usar puertos de terminación y que el valor predeterminado <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> debe ser sin restricciones.</span><span class="sxs-lookup"><span data-stu-id="e3b6e-169">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e3b6e-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3b6e-170">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [<span data-ttu-id="e3b6e-171">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="e3b6e-171">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
