---
title: "Mitigación: Control de versiones de producto"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c4de9d7-9aba-427a-8f38-0ab9bfb8f85e
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 15648a3dfc115e55dd78eb1f074b9c4235b89f34
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="mitigation-product-versioning"></a><span data-ttu-id="90279-102">Mitigación: Control de versiones de producto</span><span class="sxs-lookup"><span data-stu-id="90279-102">Mitigation: Product Versioning</span></span>
<span data-ttu-id="90279-103">En [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] y versiones posteriores, el control de versiones del producto ha cambiado con respecto a las versiones anteriores de .NET Framework (.NET Framework 4, 4.5, 4.5.1 y 4.5.2).</span><span class="sxs-lookup"><span data-stu-id="90279-103">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] and later, product versioning has changed from the previous releases of the .NET Framework (the .NET Framework 4, 4.5, 4.5.1, and 4.5.2).</span></span>  
  
## <a name="product-versioning-changes"></a><span data-ttu-id="90279-104">Cambios en el control de versiones de producto</span><span class="sxs-lookup"><span data-stu-id="90279-104">Product versioning changes</span></span>  
 <span data-ttu-id="90279-105">Estos son los cambios detallados:</span><span class="sxs-lookup"><span data-stu-id="90279-105">The following are the detailed changes:</span></span>  
  
-   <span data-ttu-id="90279-106">El valor de la entrada `Version` en la clave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` ha cambiado a `4.6.`*xxxxx* para .NET Framework 4.6 y versiones secundarias, y a `4.7.`*xxxxx* para .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="90279-106">The value of the `Version` entry in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` key has changed to `4.6.`*xxxxx* for the .NET Framework 4.6 and its point releases, and to `4.7.`*xxxxx* for the .NET Framework 4.7.</span></span> <span data-ttu-id="90279-107">En .NET Framework 4.5, 4.5.1 y 4.5.2, tenía el formato `4.5.`*xxxxx*.</span><span class="sxs-lookup"><span data-stu-id="90279-107">In the .NET Framework 4.5, 4.5.1, and 4.5.2, it had the format `4.5.`*xxxxx*.</span></span>  
  
-   <span data-ttu-id="90279-108">El control de versiones de producto y archivo para los archivos de .NET Framework ha cambiado desde el esquema de control de versiones anterior de `4.0.30319.x` a `4.6.X.0` para .NET Framework 4.6 y las versiones secundarias, y a `4.7.X.0` para .NET Framework 4.7 y las versiones secundarias.</span><span class="sxs-lookup"><span data-stu-id="90279-108">The file and product versioning for .NET Framework files has changed from the earlier versioning scheme of `4.0.30319.x` to `4.6.X.0` for the .NET Framework 4.6 and its point releases, and to `4.7.X.0` for the .NET Framework 4.7 and its point releases.</span></span> <span data-ttu-id="90279-109">Puede consultar estos nuevos valores al ver las **Propiedades** del archivo después de haber hecho clic con el botón derecho en un archivo.</span><span class="sxs-lookup"><span data-stu-id="90279-109">You can see these new values when you view the file's **Properties** after right-clicking on a file.</span></span>  
  
-   <span data-ttu-id="90279-110">Los atributos <xref:System.Reflection.AssemblyFileVersionAttribute> y <xref:System.Reflection.AssemblyInformationalVersionAttribute> de ensamblados administrados tienen valores <xref:System.Version> con la forma `4.6.X.0` para .NET Framework 4.6 y sus versiones puntuales, y `4.7.X.0` para .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="90279-110">The <xref:System.Reflection.AssemblyFileVersionAttribute> and <xref:System.Reflection.AssemblyInformationalVersionAttribute> attributes for managed assemblies have <xref:System.Version> values in the form `4.6.X.0` for the .NET Framework 4.6 and its point releases, and `4.7.X.0` for the .NET Framework 4.7.</span></span>  
  
-   <span data-ttu-id="90279-111">En [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 4.6.1, 4.6.2 y 4.7, la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> devuelve la cadena de versión no editable `4.0.30319.42000`.</span><span class="sxs-lookup"><span data-stu-id="90279-111">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 4.6.1, 4.6.2, and 4.7, the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property returns the fixed version string `4.0.30319.42000`.</span></span> <span data-ttu-id="90279-112">En .NET Framework 4, 4.5, 4.5.1 y 4.5.2, devuelve cadenas de versión con el formato `4.0.30319.xxxxx` (por ejemplo, "4.0.30319.18010").</span><span class="sxs-lookup"><span data-stu-id="90279-112">In the .NET Framework 4, 4.5, 4.5.1, and 4.5.2, it returns version strings in the format `4.0.30319.xxxxx` (for example, "4.0.30319.18010").</span></span> <span data-ttu-id="90279-113">Tenga en cuenta que no se recomienda que el código de la aplicación tome nuevas dependencias en la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="90279-113">Note that we do not recommend application code taking any new dependency on the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property.</span></span>  
  
### <a name="handling-the-product-versioning-changes"></a><span data-ttu-id="90279-114">Administrar los cambios en el control de versiones de producto</span><span class="sxs-lookup"><span data-stu-id="90279-114">Handling the product versioning changes</span></span>  
 <span data-ttu-id="90279-115">En general, las aplicaciones deben depender de las técnicas recomendadas para detectar elementos como la versión del tiempo de ejecución de .NET Framework y el directorio de instalación:</span><span class="sxs-lookup"><span data-stu-id="90279-115">In general, applications should depend on the recommended techniques for detecting such things as the runtime version of the .NET Framework and the installation directory:</span></span>  
  
-   <span data-ttu-id="90279-116">Para detectar la versión de runtime de .NET Framework, consulte el artículo sobre la [determinación de las versiones instaladas de .NET Framework](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="90279-116">To detect the runtime version of the .NET Framework, see [How to: Determine Which .NET Framework Versions Are Installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span>  
  
-   <span data-ttu-id="90279-117">Para determinar la ruta de instalación de .NET Framework, utilice el valor de la entrada `InstallPath` en la clave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`.</span><span class="sxs-lookup"><span data-stu-id="90279-117">To determine the installation path for the .NET Framework, use the value of the `InstallPath` entry in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` key.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="90279-118">El nombre de la subclave es `NET Framework Setup`, no `.NET Framework Setup`.</span><span class="sxs-lookup"><span data-stu-id="90279-118">The subkey name is `NET Framework Setup`, not `.NET Framework Setup`.</span></span>  
  
-   <span data-ttu-id="90279-119">Para determinar la ruta de acceso de directorio a Common Language Runtime de .NET Framework, llame al método <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="90279-119">To determine the directory path to the .NET Framework common language runtime, call the <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="90279-120">Para obtener la versión de CLR, llame al método <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="90279-120">To get the CLR version, call the <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion%2A?displayProperty=nameWithType> method.</span></span>   <span data-ttu-id="90279-121">Para .NET Framework 4 y sus versiones secundarias (.NET Framework 4.5, 4.5.1, 4.5.2 y [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 4.6.1, 4.6.2 y 4.7), devuelve la cadena `v4.0.30319`.</span><span class="sxs-lookup"><span data-stu-id="90279-121">For the .NET Framework 4 and its point releases (the .NET Framework 4.5, 4.5.1, 4.5.2, and [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 4.6.1, 4.6.2, and 4.7), it returns the string `v4.0.30319`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90279-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="90279-122">See Also</span></span>  
 [<span data-ttu-id="90279-123">Cambios en el runtime</span><span class="sxs-lookup"><span data-stu-id="90279-123">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)
 
