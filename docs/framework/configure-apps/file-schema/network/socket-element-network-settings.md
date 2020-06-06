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
ms.openlocfilehash: 0e2b369eccfbc658a790ef61a961315a88361669
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089086"
---
# <a name="socket-element-network-settings"></a><span data-ttu-id="4d6f5-102">Elemento \<socket> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="4d6f5-102">\<socket> Element (Network Settings)</span></span>
<span data-ttu-id="4d6f5-103">Especifica si las operaciones de socket utilizan puertos de finalización.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-103">Specifies whether socket operations use completion ports.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<socket>**

## <a name="syntax"></a><span data-ttu-id="4d6f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d6f5-104">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d6f5-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4d6f5-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4d6f5-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d6f5-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="4d6f5-107">Attributes</span></span>  
  
|<span data-ttu-id="4d6f5-108">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="4d6f5-108">**Attribute**</span></span>|<span data-ttu-id="4d6f5-109">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4d6f5-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="4d6f5-110">Indica si el socket siempre debe utilizar los puertos de finalización para las llamadas al método Accept.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-110">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="4d6f5-111">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-111">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="4d6f5-112">Indica si el socket siempre debe utilizar los puertos de finalización para las llamadas al método Connect.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-112">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="4d6f5-113">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-113">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="4d6f5-114">Especifica el valor predeterminado <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> que se va a usar para un socket.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-114">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="4d6f5-115">El valor predeterminado depende de la versión de Windows.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-115">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d6f5-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4d6f5-116">Child Elements</span></span>  
 <span data-ttu-id="4d6f5-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d6f5-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4d6f5-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4d6f5-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="4d6f5-119">**Element**</span></span>|<span data-ttu-id="4d6f5-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4d6f5-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4d6f5-121">settings</span><span class="sxs-lookup"><span data-stu-id="4d6f5-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="4d6f5-122">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d6f5-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4d6f5-123">Remarks</span></span>  
 <span data-ttu-id="4d6f5-124">Los `alwaysUseCompletionPortsForAccept` `alwaysUseCompletionPortsForConnect` atributos y se usan para especificar el comportamiento predeterminado con respecto al uso de puertos de finalización por las clases del <xref:System.Net.Sockets?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-124">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="4d6f5-125">Los puertos de finalización se recomiendan para las aplicaciones de servidor de alto rendimiento.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-125">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="4d6f5-126">El valor predeterminado de los `alwaysUseCompletionPortsForAccept` `alwaysUseCompletionPortsForConnect` atributos y es **false**.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-126">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="4d6f5-127"><xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A>Se puede usar para obtener el valor actual del `alwaysUseCompletionPortsForAccept` atributo desde los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-127">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="4d6f5-128"><xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A>Se puede usar para obtener el valor actual del `alwaysUseCompletionPortsForConnect` atributo desde los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-128">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="4d6f5-129">El `ipProtectionLevel` atributo especifica el valor predeterminado <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> que se va a usar para un socket.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-129">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="4d6f5-130">La <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> propiedad habilita la configuración de una restricción para un socket IPv6 en un ámbito especificado, como direcciones con el mismo prefijo local de vínculo o sitio.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-130">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="4d6f5-131">Esta opción permite a las aplicaciones colocar restricciones de acceso en sockets IPv6.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-131">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="4d6f5-132">Estas restricciones permiten que una aplicación que se ejecuta en una LAN privada se fortalezca de forma sencilla frente a ataques externos.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-132">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="4d6f5-133">Esta opción amplía o reduce el ámbito de un socket de escucha, lo que permite el acceso no restringido de usuarios públicos y privados cuando sea adecuado, o restringiendo el acceso únicamente al mismo sitio, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-133">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="4d6f5-134">Esta `ipProtectionLevel` configuración de atributo solo afecta al tráfico entrante inicial:</span><span class="sxs-lookup"><span data-stu-id="4d6f5-134">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
- <span data-ttu-id="4d6f5-135">Un servidor TCP que escucha las conexiones entrantes en un socket.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-135">A TCP server listening for incoming connections on a socket.</span></span>  
  
- <span data-ttu-id="4d6f5-136">Aplicación UDP que recibe un paquete en un socket.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-136">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="4d6f5-137">Esta opción de configuración no afecta a las conexiones TCP ya establecidas (el tráfico no está restringido en ambas direcciones) y no afecta a una aplicación que envía paquetes UDP.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-137">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="4d6f5-138">Los valores posibles para la `ipProtectionLevel` configuración de atributo se corresponden con los niveles de protección definidos en la <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeración de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="4d6f5-138">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|<span data-ttu-id="4d6f5-139">**Valor del atributo**</span><span class="sxs-lookup"><span data-stu-id="4d6f5-139">**Attribute Value**</span></span>|<span data-ttu-id="4d6f5-140">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4d6f5-140">**Description**</span></span>|  
|-|-|  
|<span data-ttu-id="4d6f5-141">EdgeRestricted</span><span class="sxs-lookup"><span data-stu-id="4d6f5-141">EdgeRestricted</span></span>|<span data-ttu-id="4d6f5-142">El nivel de protección de IP tiene una restricción perimetral.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-142">The IP protection level is edge restricted.</span></span> <span data-ttu-id="4d6f5-143">Este valor lo usan las aplicaciones diseñadas para funcionar a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-143">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="4d6f5-144">Este valor no permite NAT (Traducción de direcciones de red) transversal mediante la implementación de Teredo en Windows.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-144">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="4d6f5-145">Estas aplicaciones pueden eludir los firewalls de IPv4, lo que hace necesario protegerlas frente a los ataques por Internet dirigidos al puerto abierto.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-145">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="4d6f5-146">En Windows Server 2003 y Windows XP, el valor predeterminado para el nivel de protección de IP en un socket es la restricción perimetral.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-146">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="4d6f5-147">Restringido</span><span class="sxs-lookup"><span data-stu-id="4d6f5-147">Restricted</span></span>|<span data-ttu-id="4d6f5-148">El nivel de protección de IP está restringido.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-148">The IP protection level is restricted.</span></span> <span data-ttu-id="4d6f5-149">Este valor lo usan las aplicaciones de intranet que no implementan escenarios de Internet.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-149">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="4d6f5-150">Estas aplicaciones no se suelen probar ni proteger frente a los ataques por Internet.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-150">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="4d6f5-151">Este valor limitará el tráfico recibido a las direcciones locales de vínculo.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-151">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="4d6f5-152">Sin restricciones</span><span class="sxs-lookup"><span data-stu-id="4d6f5-152">Unrestricted</span></span>|<span data-ttu-id="4d6f5-153">El nivel de protección de IP no está restringido.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-153">The IP protection level is unrestricted.</span></span> <span data-ttu-id="4d6f5-154">Este valor lo usan las aplicaciones diseñadas para funcionar a través de Internet, incluidas las aplicaciones que aprovechan las funciones de NAT transversal de IPv6 integradas en Windows (por ejemplo, Teredo).</span><span class="sxs-lookup"><span data-stu-id="4d6f5-154">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="4d6f5-155">Estas aplicaciones pueden eludir los firewalls de IPv4, lo que hace necesario protegerlas frente a los ataques por Internet dirigidos al puerto abierto.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-155">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="4d6f5-156">En Windows Server 2008 R2 y Windows Vista, el valor predeterminado para el nivel de protección de IP en un socket es no restringido.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-156">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="4d6f5-157">Sin especificar</span><span class="sxs-lookup"><span data-stu-id="4d6f5-157">Unspecified</span></span>|<span data-ttu-id="4d6f5-158">El nivel de protección de IP no está especificado.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-158">The IP protection level is unspecified.</span></span> <span data-ttu-id="4d6f5-159">En Windows 7 y Windows Server 2008 R2, este es el valor predeterminado para el nivel de protección de IP en un socket.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-159">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="4d6f5-160">`ipProtectionLevel`No se **especifica**el valor predeterminado del atributo.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-160">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="4d6f5-161">La <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> propiedad se puede utilizar para obtener el valor actual del `ipProtectionLevel` atributo desde los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-161">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4d6f5-162">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="4d6f5-162">Configuration Files</span></span>  
 <span data-ttu-id="4d6f5-163">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4d6f5-163">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d6f5-164">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4d6f5-164">Example</span></span>  
 <span data-ttu-id="4d6f5-165">En el ejemplo siguiente se muestra cómo especificar que se deben usar los puertos de finalización y que el valor predeterminado <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> debe ser no restringido.</span><span class="sxs-lookup"><span data-stu-id="4d6f5-165">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4d6f5-166">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d6f5-166">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [<span data-ttu-id="4d6f5-167">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="4d6f5-167">Network Settings Schema</span></span>](index.md)
