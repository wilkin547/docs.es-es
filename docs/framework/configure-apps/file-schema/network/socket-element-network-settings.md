---
title: Elemento <socket> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
ms.openlocfilehash: aa455945b839ada4100138d5bdf9fc239376e5cb
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663987"
---
# <a name="socket-element-network-settings"></a><span data-ttu-id="d9137-102">\<Socket > (elemento, configuración de red)</span><span class="sxs-lookup"><span data-stu-id="d9137-102">\<socket> Element (Network Settings)</span></span>
<span data-ttu-id="d9137-103">Especifica si las operaciones de socket utilizan puertos de finalización.</span><span class="sxs-lookup"><span data-stu-id="d9137-103">Specifies whether socket operations use completion ports.</span></span>  
  
 <span data-ttu-id="d9137-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d9137-104">\<configuration></span></span>  
<span data-ttu-id="d9137-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="d9137-105">\<system.net></span></span>  
<span data-ttu-id="d9137-106">\<> de configuración</span><span class="sxs-lookup"><span data-stu-id="d9137-106">\<settings></span></span>  
<span data-ttu-id="d9137-107">\<> de socket</span><span class="sxs-lookup"><span data-stu-id="d9137-107">\<socket></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9137-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9137-108">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9137-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d9137-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d9137-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d9137-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9137-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="d9137-111">Attributes</span></span>  
  
|<span data-ttu-id="d9137-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="d9137-112">**Attribute**</span></span>|<span data-ttu-id="d9137-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d9137-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="d9137-114">Indica si el socket siempre debe utilizar los puertos de finalización para las llamadas al método Accept.</span><span class="sxs-lookup"><span data-stu-id="d9137-114">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="d9137-115">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="d9137-115">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="d9137-116">Indica si el socket siempre debe utilizar los puertos de finalización para las llamadas al método Connect.</span><span class="sxs-lookup"><span data-stu-id="d9137-116">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="d9137-117">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="d9137-117">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="d9137-118">Especifica el valor <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> predeterminado que se va a usar para un socket.</span><span class="sxs-lookup"><span data-stu-id="d9137-118">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="d9137-119">El valor predeterminado depende de la versión de Windows.</span><span class="sxs-lookup"><span data-stu-id="d9137-119">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d9137-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d9137-120">Child Elements</span></span>  
 <span data-ttu-id="d9137-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d9137-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d9137-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d9137-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d9137-123">**Element**</span><span class="sxs-lookup"><span data-stu-id="d9137-123">**Element**</span></span>|<span data-ttu-id="d9137-124">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d9137-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d9137-125">Configuración</span><span class="sxs-lookup"><span data-stu-id="d9137-125">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="d9137-126">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="d9137-126">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9137-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d9137-127">Remarks</span></span>  
 <span data-ttu-id="d9137-128">Los `alwaysUseCompletionPortsForAccept` atributos `alwaysUseCompletionPortsForConnect` y se usan para especificar el comportamiento predeterminado con respecto al uso de puertos de finalización <xref:System.Net.Sockets?displayProperty=nameWithType>por las clases del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="d9137-128">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="d9137-129">Los puertos de finalización se recomiendan para las aplicaciones de servidor de alto rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d9137-129">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="d9137-130">El valor predeterminado de los `alwaysUseCompletionPortsForAccept` atributos `alwaysUseCompletionPortsForConnect` y es **false**.</span><span class="sxs-lookup"><span data-stu-id="d9137-130">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="d9137-131">Se puede usar para obtener el valor actual `alwaysUseCompletionPortsForAccept` del atributo desde los archivos de configuración aplicables. <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A></span><span class="sxs-lookup"><span data-stu-id="d9137-131">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="d9137-132">Se puede usar para obtener el valor actual `alwaysUseCompletionPortsForConnect` del atributo desde los archivos de configuración aplicables. <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A></span><span class="sxs-lookup"><span data-stu-id="d9137-132">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="d9137-133">El `ipProtectionLevel` atributo especifica el valor <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> predeterminado que se va a usar para un socket.</span><span class="sxs-lookup"><span data-stu-id="d9137-133">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="d9137-134">La <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> propiedad habilita la configuración de una restricción para un socket IPv6 en un ámbito especificado, como direcciones con el mismo prefijo local de vínculo o sitio.</span><span class="sxs-lookup"><span data-stu-id="d9137-134">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="d9137-135">Esta opción permite a las aplicaciones colocar restricciones de acceso en sockets IPv6.</span><span class="sxs-lookup"><span data-stu-id="d9137-135">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="d9137-136">Estas restricciones permiten que una aplicación que se ejecuta en una LAN privada se fortalezca de forma sencilla frente a ataques externos.</span><span class="sxs-lookup"><span data-stu-id="d9137-136">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="d9137-137">Esta opción amplía o reduce el ámbito de un socket de escucha, lo que permite el acceso no restringido de usuarios públicos y privados cuando sea adecuado, o restringiendo el acceso únicamente al mismo sitio, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d9137-137">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="d9137-138">Esta `ipProtectionLevel` configuración de atributo solo afecta al tráfico entrante inicial:</span><span class="sxs-lookup"><span data-stu-id="d9137-138">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
- <span data-ttu-id="d9137-139">Un servidor TCP que escucha las conexiones entrantes en un socket.</span><span class="sxs-lookup"><span data-stu-id="d9137-139">A TCP server listening for incoming connections on a socket.</span></span>  
  
- <span data-ttu-id="d9137-140">Aplicación UDP que recibe un paquete en un socket.</span><span class="sxs-lookup"><span data-stu-id="d9137-140">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="d9137-141">Esta opción de configuración no afecta a las conexiones TCP ya establecidas (el tráfico no está restringido en ambas direcciones) y no afecta a una aplicación que envía paquetes UDP.</span><span class="sxs-lookup"><span data-stu-id="d9137-141">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="d9137-142">Los valores posibles para la `ipProtectionLevel` configuración de atributo se corresponden con los niveles de protección definidos <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> en la enumeración de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="d9137-142">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|<span data-ttu-id="d9137-143">**Valor de atributo**</span><span class="sxs-lookup"><span data-stu-id="d9137-143">**Attribute Value**</span></span>|<span data-ttu-id="d9137-144">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d9137-144">**Description**</span></span>|  
|-|-|  
|<span data-ttu-id="d9137-145">EdgeRestricted</span><span class="sxs-lookup"><span data-stu-id="d9137-145">EdgeRestricted</span></span>|<span data-ttu-id="d9137-146">El nivel de protección de IP tiene restricción perimetral.</span><span class="sxs-lookup"><span data-stu-id="d9137-146">The IP protection level is edge restricted.</span></span> <span data-ttu-id="d9137-147">Este valor lo usan las aplicaciones diseñadas para funcionar a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="d9137-147">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="d9137-148">Esta configuración no permite la exploración transversal de la traducción de direcciones de red (NAT) mediante la implementación de Teredo de Windows.</span><span class="sxs-lookup"><span data-stu-id="d9137-148">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="d9137-149">Estas aplicaciones pueden eludir los firewalls IPv4, por lo que las aplicaciones deben protegerse frente a ataques por Internet dirigidos al puerto abierto.</span><span class="sxs-lookup"><span data-stu-id="d9137-149">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="d9137-150">En Windows Server 2003 y Windows XP, el valor predeterminado para el nivel de protección de IP en un socket es el restringido perimetral.</span><span class="sxs-lookup"><span data-stu-id="d9137-150">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="d9137-151">Restringido</span><span class="sxs-lookup"><span data-stu-id="d9137-151">Restricted</span></span>|<span data-ttu-id="d9137-152">El nivel de protección de IP está restringido.</span><span class="sxs-lookup"><span data-stu-id="d9137-152">The IP protection level is restricted.</span></span> <span data-ttu-id="d9137-153">Este valor lo usan las aplicaciones de intranet que no implementan escenarios de Internet.</span><span class="sxs-lookup"><span data-stu-id="d9137-153">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="d9137-154">Normalmente, estas aplicaciones no se comprueban ni protegen frente a ataques de tipo Internet.</span><span class="sxs-lookup"><span data-stu-id="d9137-154">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="d9137-155">Esta configuración limitará el tráfico recibido solo a vínculo local.</span><span class="sxs-lookup"><span data-stu-id="d9137-155">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="d9137-156">Sin restricción</span><span class="sxs-lookup"><span data-stu-id="d9137-156">Unrestricted</span></span>|<span data-ttu-id="d9137-157">El nivel de protección de IP no está restringido.</span><span class="sxs-lookup"><span data-stu-id="d9137-157">The IP protection level is unrestricted.</span></span> <span data-ttu-id="d9137-158">Este valor lo usan las aplicaciones diseñadas para funcionar a través de Internet, incluidas las aplicaciones que aprovechan las capacidades de NAT transversal de IPv6 integradas en Windows (por ejemplo, Teredo).</span><span class="sxs-lookup"><span data-stu-id="d9137-158">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="d9137-159">Estas aplicaciones pueden eludir los firewalls IPv4, por lo que las aplicaciones deben protegerse frente a ataques por Internet dirigidos al puerto abierto.</span><span class="sxs-lookup"><span data-stu-id="d9137-159">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="d9137-160">En Windows Server 2008 R2 y Windows Vista, el valor predeterminado para el nivel de protección de IP en un socket es Unrestricted.</span><span class="sxs-lookup"><span data-stu-id="d9137-160">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="d9137-161">Sin especificar</span><span class="sxs-lookup"><span data-stu-id="d9137-161">Unspecified</span></span>|<span data-ttu-id="d9137-162">El nivel de protección de IP no está especificado.</span><span class="sxs-lookup"><span data-stu-id="d9137-162">The IP protection level is unspecified.</span></span> <span data-ttu-id="d9137-163">En Windows 7 y Windows Server 2008 R2, no se especifica el valor predeterminado para el nivel de protección de IP en un socket.</span><span class="sxs-lookup"><span data-stu-id="d9137-163">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="d9137-164">No se especifica el valor `ipProtectionLevel` predeterminado delatributo.</span><span class="sxs-lookup"><span data-stu-id="d9137-164">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="d9137-165">La <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> propiedad se puede utilizar para obtener el valor actual `ipProtectionLevel` del atributo desde los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="d9137-165">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d9137-166">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="d9137-166">Configuration Files</span></span>  
 <span data-ttu-id="d9137-167">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="d9137-167">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9137-168">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d9137-168">Example</span></span>  
 <span data-ttu-id="d9137-169">En el ejemplo siguiente se muestra cómo especificar que se deben usar los puertos de finalización <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> y que el valor predeterminado debe ser no restringido.</span><span class="sxs-lookup"><span data-stu-id="d9137-169">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d9137-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9137-170">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [<span data-ttu-id="d9137-171">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="d9137-171">Network Settings Schema</span></span>](index.md)
