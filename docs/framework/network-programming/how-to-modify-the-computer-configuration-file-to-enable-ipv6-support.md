---
title: Procedimiento para modificar el archivo de configuración de equipo para habilitar la compatibilidad con IPv6
ms.date: 03/30/2017
ms.assetid: 5611b677-b9cc-43b8-a434-60e18d89aada
ms.openlocfilehash: 362e7af36d214df9f0454479e25a80af9d440b2b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71048286"
---
# <a name="how-to-modify-the-computer-configuration-file-to-enable-ipv6-support"></a><span data-ttu-id="e84f4-102">Procedimiento para modificar el archivo de configuración de equipo para habilitar la compatibilidad con IPv6</span><span class="sxs-lookup"><span data-stu-id="e84f4-102">How to: Modify the Computer Configuration File to Enable IPv6 Support</span></span>
<span data-ttu-id="e84f4-103">En el ejemplo de código siguiente se muestra cómo modificar el archivo de configuración de equipo, *machine.config*, para permitir la compatibilidad con IPv6.</span><span class="sxs-lookup"><span data-stu-id="e84f4-103">The following code example shows how to modify the computer configuration file, *machine.config*, to enable IPv6 support.</span></span> <span data-ttu-id="e84f4-104">El archivo *machine.config* se almacena en la carpeta *%Windir%\Microsoft.NET\Framework* en el directorio donde se ha instalado Windows.</span><span class="sxs-lookup"><span data-stu-id="e84f4-104">The *machine.config* file is stored in the *%Windir%\Microsoft.NET\Framework* folder in the directory where Windows was installed.</span></span> <span data-ttu-id="e84f4-105">Hay un archivo *machine.config* distinto en las carpetas bajo *%Windir%\Microsoft.NET\Framework* para cada versión de .NET Framework instalada en el equipo (por ejemplo, *C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config*).</span><span class="sxs-lookup"><span data-stu-id="e84f4-105">There is a separate *machine.config* file in the folders under *%Windir%\Microsoft.NET\Framework* for each version of the .NET Framework installed on the computer (for example, *C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config*).</span></span>  
  
 <span data-ttu-id="e84f4-106">Estos valores se pueden crear también en el archivo de configuración de la aplicación, que tiene prioridad sobre el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="e84f4-106">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>  
  
 <span data-ttu-id="e84f4-107">Para .NET Framework versión 1.1 y anterior, el valor del modificador de la configuración **ipv6 enabled** especifica si los miembros de la clase <xref:System.Net.Dns?displayProperty=nameWithType> devuelven las direcciones de IPv6.</span><span class="sxs-lookup"><span data-stu-id="e84f4-107">For .NET Framework version 1.1 and earlier, the value of the **ipv6 enabled** configuration switch specifies whether members of the <xref:System.Net.Dns?displayProperty=nameWithType> class return IPv6 addresses.</span></span>  
  
 <span data-ttu-id="e84f4-108">En la versión 2.0 de .NET Framework y versiones posteriores, si Windows admite IPv6, entonces todos los miembros de la clase <xref:System.Net.Dns?displayProperty=nameWithType> (por ejemplo, el método <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType>), devolverán las direcciones de IPv6 con una limitación.</span><span class="sxs-lookup"><span data-stu-id="e84f4-108">For .NET Framework version 2.0 and later, if Windows supports IPv6, then all members of the <xref:System.Net.Dns?displayProperty=nameWithType> class (for example, the <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> method), will return IPv6 addresses with one limitation.</span></span> <span data-ttu-id="e84f4-109">Los miembros obsoletos de la clase <xref:System.Net.Dns?displayProperty=nameWithType> (por ejemplo, el método <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType>) leerán y reconocerán el valor en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e84f4-109">Obsolete members of the <xref:System.Net.Dns?displayProperty=nameWithType> class (for example, the <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> method) will read and recognize the value in the configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e84f4-110">En la versión 2.0 de .NET Framework y versiones posteriores, IPv6 está habilitada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e84f4-110">For .NET Framework version 2.0 and later, IPv6 is enabled by default.</span></span> <span data-ttu-id="e84f4-111">Para .NET Framework versión 1.1 y anteriores, IPv6 está deshabilitada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e84f4-111">For .NET Framework version 1.1 and earlier, IPv6 is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e84f4-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e84f4-112">Example</span></span>  
  
```xml  
<system.net>  
    …………  
    <settings>  
        …………  
        <ipv6 enabled="true"/>   
    ……………  
    </settings>  
    ………………  
<system.net>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e84f4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e84f4-113">See also</span></span>

- [<span data-ttu-id="e84f4-114">Direccionamiento IPv6</span><span class="sxs-lookup"><span data-stu-id="e84f4-114">IPv6 Addressing</span></span>](ipv6-addressing.md)
- [<span data-ttu-id="e84f4-115">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="e84f4-115">Network Settings Schema</span></span>](../configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="e84f4-116">Elemento \<ipv6> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="e84f4-116">\<ipv6> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/ipv6-element-network-settings.md)
