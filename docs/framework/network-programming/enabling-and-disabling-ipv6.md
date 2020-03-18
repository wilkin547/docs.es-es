---
title: Habilitar y deshabilitar IPv6
ms.date: 03/30/2017
ms.assetid: 6408d3ef-c9ba-49d9-b15e-fe74bd3ef031
ms.openlocfilehash: 66c802dd5feb865faf7469cb7da04fbffcb4a2d6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048564"
---
# <a name="enabling-and-disabling-ipv6"></a><span data-ttu-id="5ff00-102">Habilitar y deshabilitar IPv6</span><span class="sxs-lookup"><span data-stu-id="5ff00-102">Enabling and Disabling IPv6</span></span>
<span data-ttu-id="5ff00-103">Para usar el protocolo IPv6, asegúrese de que está ejecutando una versión del sistema operativo que admita IPv6 y asegúrese de que el sistema operativo y las clases de red están configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="5ff00-103">To use the IPv6 protocol, ensure that you are running a version of the operating system that supports IPv6 and ensure that the operating system and the networking classes are configured properly.</span></span>  
  
## <a name="configuration-steps"></a><span data-ttu-id="5ff00-104">Pasos de la configuración</span><span class="sxs-lookup"><span data-stu-id="5ff00-104">Configuration Steps</span></span>  
 <span data-ttu-id="5ff00-105">En la tabla siguiente se muestran varias configuraciones</span><span class="sxs-lookup"><span data-stu-id="5ff00-105">The following table lists various configurations</span></span>  
  
|<span data-ttu-id="5ff00-106">¿El sistema operativo está habilitado para IPv6?</span><span class="sxs-lookup"><span data-stu-id="5ff00-106">Operating system IPv6-enabled?</span></span>|<span data-ttu-id="5ff00-107">¿Las clases de red están habilitadas para IPv6?</span><span class="sxs-lookup"><span data-stu-id="5ff00-107">Networking classes IPv6-enabled?</span></span>|<span data-ttu-id="5ff00-108">Description</span><span class="sxs-lookup"><span data-stu-id="5ff00-108">Description</span></span>|  
|-------------------------------------|---------------------------------------|-----------------|  
|<span data-ttu-id="5ff00-109">No</span><span class="sxs-lookup"><span data-stu-id="5ff00-109">No</span></span>|<span data-ttu-id="5ff00-110">No</span><span class="sxs-lookup"><span data-stu-id="5ff00-110">No</span></span>|<span data-ttu-id="5ff00-111">Puede analizar las direcciones de IPv6.</span><span class="sxs-lookup"><span data-stu-id="5ff00-111">Can parse IPv6 addresses.</span></span>|  
|<span data-ttu-id="5ff00-112">No</span><span class="sxs-lookup"><span data-stu-id="5ff00-112">No</span></span>|<span data-ttu-id="5ff00-113">Sí</span><span class="sxs-lookup"><span data-stu-id="5ff00-113">Yes</span></span>|<span data-ttu-id="5ff00-114">Puede analizar las direcciones de IPv6.</span><span class="sxs-lookup"><span data-stu-id="5ff00-114">Can parse IPv6 addresses.</span></span>|  
|<span data-ttu-id="5ff00-115">Sí</span><span class="sxs-lookup"><span data-stu-id="5ff00-115">Yes</span></span>|<span data-ttu-id="5ff00-116">No</span><span class="sxs-lookup"><span data-stu-id="5ff00-116">No</span></span>|<span data-ttu-id="5ff00-117">Puede analizar las direcciones de IPv6 y resolver las direcciones de IPv6 mediante métodos de resolución de nombres que no se hayan marcado como obsoletos.</span><span class="sxs-lookup"><span data-stu-id="5ff00-117">Can parse IPv6 addresses and resolve IPv6 addresses using name resolution methods not marked obsolete.</span></span>|  
|<span data-ttu-id="5ff00-118">Sí</span><span class="sxs-lookup"><span data-stu-id="5ff00-118">Yes</span></span>|<span data-ttu-id="5ff00-119">Sí</span><span class="sxs-lookup"><span data-stu-id="5ff00-119">Yes</span></span>|<span data-ttu-id="5ff00-120">Puede analizar y resolver las direcciones de IPv6 con todos los métodos, incluidos los que se hayan marcado como obsoletos.</span><span class="sxs-lookup"><span data-stu-id="5ff00-120">Can parse and resolve IPv6 addresses using all methods including those marked obsolete.</span></span>|  
  
 <span data-ttu-id="5ff00-121">Tenga en cuenta que para habilitar la compatibilidad con IPv6 para todas las clases del espacio de nombres System.Net, debe modificar el archivo de configuración del equipo o el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5ff00-121">Be aware that to enable the IPv6 support for all classes in the System.Net namespace, you must modify the computer configuration file or the configuration file for the application.</span></span> <span data-ttu-id="5ff00-122">El archivo de configuración de la aplicación tiene prioridad sobre el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="5ff00-122">The configuration file for an application has precedence over the computer configuration file.</span></span>  
  
 <span data-ttu-id="5ff00-123">Para obtener un ejemplo de cómo modificar el archivo de configuración del equipo, *machine.config*, para habilitar la compatibilidad con IPv6, vea [Cómo: modificar el archivo de configuración de equipo para habilitar la compatibilidad con IPv6](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span><span class="sxs-lookup"><span data-stu-id="5ff00-123">For an example of how to modify the computer configuration file, *machine.config*, to enable Ipv6 support see, [How to: Modify the Computer Configuration File to Enable Ipv6 Support](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span></span> <span data-ttu-id="5ff00-124">Además, asegúrese de que la compatibilidad con IPv6 está habilitada para el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5ff00-124">Also, ensure that the IPv6 support is enabled for the operating system.</span></span>  
  
 <span data-ttu-id="5ff00-125">.NET Framework tiene un modificador de configuración establecido en un archivo de configuración como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="5ff00-125">The .NET Framework has a configuration switch set in a configuration file as follows</span></span>  
  
```xml  
<system.net>  
  ...  
  <settings>  
    ...  
    <ipv6 enabled="true"/>  
    ...  
  </settings>  
  ...  
</system.net>  
```  
  
 <span data-ttu-id="5ff00-126">Para .NET Framework versión 1.1 y anterior, el valor del modificador de la configuración **ipv6 enabled** especifica si los miembros de la clase <xref:System.Net.Dns?displayProperty=nameWithType> devuelven las direcciones de IPv6.</span><span class="sxs-lookup"><span data-stu-id="5ff00-126">For .NET Framework version 1.1 and earlier, the value of the **ipv6 enabled** configuration switch specifies whether members of the <xref:System.Net.Dns?displayProperty=nameWithType> class return IPv6 addresses.</span></span>  
  
 <span data-ttu-id="5ff00-127">En la versión 2.0 de .NET Framework y versiones posteriores, si Windows admite IPv6, entonces los miembros de la clase <xref:System.Net.Dns?displayProperty=nameWithType> (por ejemplo, el método <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType>), devolverán las direcciones de IPv6 con una limitación.</span><span class="sxs-lookup"><span data-stu-id="5ff00-127">For .NET Framework version 2.0 and later, if Windows supports IPv6, then members of the <xref:System.Net.Dns?displayProperty=nameWithType> class, (for example, the <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> method), will return IPv6 addresses with one limitation.</span></span> <span data-ttu-id="5ff00-128">Los miembros obsoletos del DNS <xref:System.Net.Dns?displayProperty=nameWithType> (por ejemplo, el método <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType>) leerán y reconocerán el valor en el archivo de configuración para la configuración habilitada para IPv6.</span><span class="sxs-lookup"><span data-stu-id="5ff00-128">Obsolete members of the DNS <xref:System.Net.Dns?displayProperty=nameWithType> (for example, the <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> method) will read and recognize the value in the configuration file for the ipv6 enabled setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff00-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ff00-129">See also</span></span>

- [<span data-ttu-id="5ff00-130">Protocolo de Internet versión 6</span><span class="sxs-lookup"><span data-stu-id="5ff00-130">Internet Protocol Version 6</span></span>](internet-protocol-version-6.md)
- [<span data-ttu-id="5ff00-131">Sockets</span><span class="sxs-lookup"><span data-stu-id="5ff00-131">Sockets</span></span>](sockets.md)
- [<span data-ttu-id="5ff00-132">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="5ff00-132">Network Settings Schema</span></span>](../configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="5ff00-133">Elemento \<ipv6> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="5ff00-133">\<ipv6> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/ipv6-element-network-settings.md)
