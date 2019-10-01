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
ms.openlocfilehash: ec2c8388411e24940041dc9dcb7f6a6755e89805
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697588"
---
# <a name="socket-element-network-settings"></a><span data-ttu-id="eafc5-102">\<socket (elemento >) (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="eafc5-102">\<socket> Element (Network Settings)</span></span>
<span data-ttu-id="eafc5-103">Especifica si las operaciones de socket utilizan puertos de finalización.</span><span class="sxs-lookup"><span data-stu-id="eafc5-103">Specifies whether socket operations use completion ports.</span></span>  
  
[<span data-ttu-id="eafc5-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="eafc5-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="eafc5-105">&nbsp; @ no__t-1[ **@no__t -4System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="eafc5-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="eafc5-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<settings >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="eafc5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>  
<span data-ttu-id="eafc5-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<socket >**</span><span class="sxs-lookup"><span data-stu-id="eafc5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<socket>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eafc5-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eafc5-108">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eafc5-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="eafc5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="eafc5-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="eafc5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eafc5-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="eafc5-111">Attributes</span></span>  
  
|<span data-ttu-id="eafc5-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="eafc5-112">**Attribute**</span></span>|<span data-ttu-id="eafc5-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="eafc5-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="eafc5-114">Indica si el socket siempre debe utilizar los puertos de finalización para las llamadas al método Accept.</span><span class="sxs-lookup"><span data-stu-id="eafc5-114">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="eafc5-115">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="eafc5-115">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="eafc5-116">Indica si el socket siempre debe utilizar los puertos de finalización para las llamadas al método Connect.</span><span class="sxs-lookup"><span data-stu-id="eafc5-116">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="eafc5-117">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="eafc5-117">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="eafc5-118">Especifica el valor predeterminado <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> que se va a usar para un socket.</span><span class="sxs-lookup"><span data-stu-id="eafc5-118">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="eafc5-119">El valor predeterminado depende de la versión de Windows.</span><span class="sxs-lookup"><span data-stu-id="eafc5-119">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eafc5-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="eafc5-120">Child Elements</span></span>  
 <span data-ttu-id="eafc5-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="eafc5-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eafc5-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="eafc5-122">Parent Elements</span></span>  
  
|<span data-ttu-id="eafc5-123">**Element**</span><span class="sxs-lookup"><span data-stu-id="eafc5-123">**Element**</span></span>|<span data-ttu-id="eafc5-124">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="eafc5-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="eafc5-125">Configuración</span><span class="sxs-lookup"><span data-stu-id="eafc5-125">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="eafc5-126">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="eafc5-126">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eafc5-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eafc5-127">Remarks</span></span>  
 <span data-ttu-id="eafc5-128">Los atributos `alwaysUseCompletionPortsForAccept` y `alwaysUseCompletionPortsForConnect` se utilizan para especificar el comportamiento predeterminado relacionado con el uso de los puertos de finalización por las clases de la @no__t -2. Namespace.</span><span class="sxs-lookup"><span data-stu-id="eafc5-128">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="eafc5-129">Los puertos de finalización se recomiendan para las aplicaciones de servidor de alto rendimiento.</span><span class="sxs-lookup"><span data-stu-id="eafc5-129">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="eafc5-130">El valor predeterminado de los atributos `alwaysUseCompletionPortsForAccept` y `alwaysUseCompletionPortsForConnect` es **false**.</span><span class="sxs-lookup"><span data-stu-id="eafc5-130">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="eafc5-131">Se puede usar <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> para obtener el valor actual del atributo `alwaysUseCompletionPortsForAccept` de los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="eafc5-131">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="eafc5-132">Se puede usar <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> para obtener el valor actual del atributo `alwaysUseCompletionPortsForConnect` de los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="eafc5-132">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="eafc5-133">El atributo `ipProtectionLevel` especifica el @no__t predeterminado-1 que se va a usar para un socket.</span><span class="sxs-lookup"><span data-stu-id="eafc5-133">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="eafc5-134">La propiedad <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> permite configurar una restricción para un socket IPv6 a un ámbito especificado, como direcciones con el mismo prefijo local de vínculo o sitio.</span><span class="sxs-lookup"><span data-stu-id="eafc5-134">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="eafc5-135">Esta opción permite a las aplicaciones colocar restricciones de acceso en sockets IPv6.</span><span class="sxs-lookup"><span data-stu-id="eafc5-135">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="eafc5-136">Estas restricciones permiten que una aplicación que se ejecuta en una LAN privada se fortalezca de forma sencilla frente a ataques externos.</span><span class="sxs-lookup"><span data-stu-id="eafc5-136">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="eafc5-137">Esta opción amplía o reduce el ámbito de un socket de escucha, lo que permite el acceso no restringido de usuarios públicos y privados cuando sea adecuado, o restringiendo el acceso únicamente al mismo sitio, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="eafc5-137">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="eafc5-138">Este valor de atributo `ipProtectionLevel` solo afecta al tráfico entrante inicial:</span><span class="sxs-lookup"><span data-stu-id="eafc5-138">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
- <span data-ttu-id="eafc5-139">Un servidor TCP que escucha las conexiones entrantes en un socket.</span><span class="sxs-lookup"><span data-stu-id="eafc5-139">A TCP server listening for incoming connections on a socket.</span></span>  
  
- <span data-ttu-id="eafc5-140">Aplicación UDP que recibe un paquete en un socket.</span><span class="sxs-lookup"><span data-stu-id="eafc5-140">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="eafc5-141">Esta opción de configuración no afecta a las conexiones TCP ya establecidas (el tráfico no está restringido en ambas direcciones) y no afecta a una aplicación que envía paquetes UDP.</span><span class="sxs-lookup"><span data-stu-id="eafc5-141">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="eafc5-142">Los valores posibles para el valor del atributo `ipProtectionLevel` se corresponden con los niveles de protección definidos en la enumeración <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="eafc5-142">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|<span data-ttu-id="eafc5-143">**Valor de atributo**</span><span class="sxs-lookup"><span data-stu-id="eafc5-143">**Attribute Value**</span></span>|<span data-ttu-id="eafc5-144">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="eafc5-144">**Description**</span></span>|  
|-|-|  
|<span data-ttu-id="eafc5-145">EdgeRestricted</span><span class="sxs-lookup"><span data-stu-id="eafc5-145">EdgeRestricted</span></span>|<span data-ttu-id="eafc5-146">El nivel de protección de IP tiene restricción perimetral.</span><span class="sxs-lookup"><span data-stu-id="eafc5-146">The IP protection level is edge restricted.</span></span> <span data-ttu-id="eafc5-147">Este valor lo usan las aplicaciones diseñadas para funcionar a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="eafc5-147">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="eafc5-148">Esta configuración no permite la exploración transversal de la traducción de direcciones de red (NAT) mediante la implementación de Teredo de Windows.</span><span class="sxs-lookup"><span data-stu-id="eafc5-148">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="eafc5-149">Estas aplicaciones pueden eludir los firewalls IPv4, por lo que las aplicaciones deben protegerse frente a ataques por Internet dirigidos al puerto abierto.</span><span class="sxs-lookup"><span data-stu-id="eafc5-149">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="eafc5-150">En Windows Server 2003 y Windows XP, el valor predeterminado para el nivel de protección de IP en un socket es el restringido perimetral.</span><span class="sxs-lookup"><span data-stu-id="eafc5-150">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="eafc5-151">Restringido</span><span class="sxs-lookup"><span data-stu-id="eafc5-151">Restricted</span></span>|<span data-ttu-id="eafc5-152">El nivel de protección de IP está restringido.</span><span class="sxs-lookup"><span data-stu-id="eafc5-152">The IP protection level is restricted.</span></span> <span data-ttu-id="eafc5-153">Este valor lo usan las aplicaciones de intranet que no implementan escenarios de Internet.</span><span class="sxs-lookup"><span data-stu-id="eafc5-153">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="eafc5-154">Normalmente, estas aplicaciones no se comprueban ni protegen frente a ataques de tipo Internet.</span><span class="sxs-lookup"><span data-stu-id="eafc5-154">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="eafc5-155">Esta configuración limitará el tráfico recibido solo a vínculo local.</span><span class="sxs-lookup"><span data-stu-id="eafc5-155">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="eafc5-156">Sin restricción</span><span class="sxs-lookup"><span data-stu-id="eafc5-156">Unrestricted</span></span>|<span data-ttu-id="eafc5-157">El nivel de protección de IP no está restringido.</span><span class="sxs-lookup"><span data-stu-id="eafc5-157">The IP protection level is unrestricted.</span></span> <span data-ttu-id="eafc5-158">Este valor lo usan las aplicaciones diseñadas para funcionar a través de Internet, incluidas las aplicaciones que aprovechan las capacidades de NAT transversal de IPv6 integradas en Windows (por ejemplo, Teredo).</span><span class="sxs-lookup"><span data-stu-id="eafc5-158">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="eafc5-159">Estas aplicaciones pueden eludir los firewalls IPv4, por lo que las aplicaciones deben protegerse frente a ataques por Internet dirigidos al puerto abierto.</span><span class="sxs-lookup"><span data-stu-id="eafc5-159">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="eafc5-160">En Windows Server 2008 R2 y Windows Vista, el valor predeterminado para el nivel de protección de IP en un socket es Unrestricted.</span><span class="sxs-lookup"><span data-stu-id="eafc5-160">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="eafc5-161">Sin especificar</span><span class="sxs-lookup"><span data-stu-id="eafc5-161">Unspecified</span></span>|<span data-ttu-id="eafc5-162">El nivel de protección de IP no está especificado.</span><span class="sxs-lookup"><span data-stu-id="eafc5-162">The IP protection level is unspecified.</span></span> <span data-ttu-id="eafc5-163">En Windows 7 y Windows Server 2008 R2, no se especifica el valor predeterminado para el nivel de protección de IP en un socket.</span><span class="sxs-lookup"><span data-stu-id="eafc5-163">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="eafc5-164">No se **especifica**el valor predeterminado del atributo `ipProtectionLevel`.</span><span class="sxs-lookup"><span data-stu-id="eafc5-164">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="eafc5-165">Se puede usar la propiedad <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> para obtener el valor actual del atributo `ipProtectionLevel` de los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="eafc5-165">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="eafc5-166">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="eafc5-166">Configuration Files</span></span>  
 <span data-ttu-id="eafc5-167">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="eafc5-167">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eafc5-168">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eafc5-168">Example</span></span>  
 <span data-ttu-id="eafc5-169">En el ejemplo siguiente se muestra cómo especificar que se deben usar los puertos de finalización y que el valor predeterminado <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> debe ser Unrestricted.</span><span class="sxs-lookup"><span data-stu-id="eafc5-169">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eafc5-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="eafc5-170">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [<span data-ttu-id="eafc5-171">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="eafc5-171">Network Settings Schema</span></span>](index.md)
