---
title: 'Mitigación: Control de versiones de producto'
description: En este artículo, aprenderá cómo ha cambiado .NET Framework 4.6 y versiones posteriores del producto con respecto a las versiones anteriores.
ms.date: 03/30/2017
ms.assetid: 1c4de9d7-9aba-427a-8f38-0ab9bfb8f85e
ms.openlocfilehash: 442c06446e763758d3a150ee9ff884a616541c07
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475403"
---
# <a name="mitigation-product-versioning"></a><span data-ttu-id="7fd52-103">Mitigación: control de versiones de producto</span><span class="sxs-lookup"><span data-stu-id="7fd52-103">Mitigation: Product Versioning</span></span>

<span data-ttu-id="7fd52-104">En .NET Framework 4.6 y versiones posteriores, el control de versiones del producto ha cambiado con respecto a las versiones anteriores de .NET Framework (.NET Framework 4, 4.5, 4.5.1 y 4.5.2).</span><span class="sxs-lookup"><span data-stu-id="7fd52-104">In the .NET Framework 4.6 and later, product versioning has changed from the previous releases of the .NET Framework (the .NET Framework 4, 4.5, 4.5.1, and 4.5.2).</span></span>

## <a name="product-versioning-changes"></a><span data-ttu-id="7fd52-105">Cambios en el control de versiones de producto</span><span class="sxs-lookup"><span data-stu-id="7fd52-105">Product versioning changes</span></span>

<span data-ttu-id="7fd52-106">Estos son los cambios detallados:</span><span class="sxs-lookup"><span data-stu-id="7fd52-106">The following are the detailed changes:</span></span>

- <span data-ttu-id="7fd52-107">El valor de la entrada `Version` en la clave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` ha cambiado a `4.6.`*xxxxx* para .NET Framework 4.6 y versiones secundarias, y a `4.7.`*xxxxx* para .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="7fd52-107">The value of the `Version` entry in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` key has changed to `4.6.`*xxxxx* for the .NET Framework 4.6 and its point releases, and to `4.7.`*xxxxx* for the .NET Framework 4.7.</span></span> <span data-ttu-id="7fd52-108">En .NET Framework 4.5, 4.5.1 y 4.5.2, tenía el formato `4.5.`*xxxxx*.</span><span class="sxs-lookup"><span data-stu-id="7fd52-108">In the .NET Framework 4.5, 4.5.1, and 4.5.2, it had the format `4.5.`*xxxxx*.</span></span>

- <span data-ttu-id="7fd52-109">El control de versiones de producto y archivo para los archivos de .NET Framework ha cambiado desde el esquema de control de versiones anterior de `4.0.30319.x` a `4.6.X.0` para .NET Framework 4.6 y las versiones secundarias, y a `4.7.X.0` para .NET Framework 4.7 y las versiones secundarias.</span><span class="sxs-lookup"><span data-stu-id="7fd52-109">The file and product versioning for .NET Framework files has changed from the earlier versioning scheme of `4.0.30319.x` to `4.6.X.0` for the .NET Framework 4.6 and its point releases, and to `4.7.X.0` for the .NET Framework 4.7 and its point releases.</span></span> <span data-ttu-id="7fd52-110">Puede consultar estos nuevos valores al ver las **Propiedades** del archivo después de haber hecho clic con el botón derecho en un archivo.</span><span class="sxs-lookup"><span data-stu-id="7fd52-110">You can see these new values when you view the file's **Properties** after right-clicking on a file.</span></span>

- <span data-ttu-id="7fd52-111">Los atributos <xref:System.Reflection.AssemblyFileVersionAttribute> y <xref:System.Reflection.AssemblyInformationalVersionAttribute> de ensamblados administrados tienen valores <xref:System.Version> con la forma `4.6.X.0` para .NET Framework 4.6 y sus versiones puntuales, y `4.7.X.0` para .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="7fd52-111">The <xref:System.Reflection.AssemblyFileVersionAttribute> and <xref:System.Reflection.AssemblyInformationalVersionAttribute> attributes for managed assemblies have <xref:System.Version> values in the form `4.6.X.0` for the .NET Framework 4.6 and its point releases, and `4.7.X.0` for the .NET Framework 4.7.</span></span>

- <span data-ttu-id="7fd52-112">A partir de .NET Framework 4.6, la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType> devuelve la cadena de versión no editable `4.0.30319.42000`.</span><span class="sxs-lookup"><span data-stu-id="7fd52-112">Starting with .NET Framework 4.6, the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property returns the fixed version string `4.0.30319.42000`.</span></span> <span data-ttu-id="7fd52-113">En .NET Framework 4, 4.5, 4.5.1 y 4.5.2, devuelve cadenas de versión con el formato `4.0.30319.xxxxx`, donde `xxxxx` es inferior a 42000 (por ejemplo, "4.0.30319.18010").</span><span class="sxs-lookup"><span data-stu-id="7fd52-113">In the .NET Framework 4, 4.5, 4.5.1, and 4.5.2, it returns version strings in the format `4.0.30319.xxxxx` where `xxxxx` is less than 42000 (for example, "4.0.30319.18010").</span></span> <span data-ttu-id="7fd52-114">Tenga en cuenta que no se recomienda que el código de la aplicación tome nuevas dependencias en la propiedad <xref:System.Environment.Version%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7fd52-114">Note that we do not recommend application code taking any new dependency on the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property.</span></span>

### <a name="handling-the-product-versioning-changes"></a><span data-ttu-id="7fd52-115">Administrar los cambios en el control de versiones de producto</span><span class="sxs-lookup"><span data-stu-id="7fd52-115">Handling the product versioning changes</span></span>

<span data-ttu-id="7fd52-116">En general, las aplicaciones deben depender de las técnicas recomendadas para detectar elementos como la versión del tiempo de ejecución de .NET Framework y el directorio de instalación:</span><span class="sxs-lookup"><span data-stu-id="7fd52-116">In general, applications should depend on the recommended techniques for detecting such things as the runtime version of the .NET Framework and the installation directory:</span></span>

- <span data-ttu-id="7fd52-117">Para detectar la versión de tiempo de ejecución de .NET Framework, vea [Cómo: Determinar qué versiones de .NET Framework están instaladas](how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="7fd52-117">To detect the runtime version of the .NET Framework, see [How to: Determine Which .NET Framework Versions Are Installed](how-to-determine-which-versions-are-installed.md).</span></span>

- <span data-ttu-id="7fd52-118">Para determinar la ruta de instalación de .NET Framework, utilice el valor de la entrada `InstallPath` en la clave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`.</span><span class="sxs-lookup"><span data-stu-id="7fd52-118">To determine the installation path for the .NET Framework, use the value of the `InstallPath` entry in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` key.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="7fd52-119">El nombre de la subclave es `NET Framework Setup`, no `.NET Framework Setup`.</span><span class="sxs-lookup"><span data-stu-id="7fd52-119">The subkey name is `NET Framework Setup`, not `.NET Framework Setup`.</span></span>

- <span data-ttu-id="7fd52-120">Para determinar la ruta de acceso de directorio a Common Language Runtime de .NET Framework, llame al método <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7fd52-120">To determine the directory path to the .NET Framework common language runtime, call the <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory%2A?displayProperty=nameWithType> method.</span></span>

- <span data-ttu-id="7fd52-121">Para obtener la versión de CLR, llame al método <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7fd52-121">To get the CLR version, call the <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion%2A?displayProperty=nameWithType> method.</span></span>   <span data-ttu-id="7fd52-122">Para .NET Framework 4 y sus versiones secundarias (.NET Framework 4.5, 4.5.1, 4.5.2 y .NET Framework 4.6, 4.6.1, 4.6.2 y 4.7), devuelve la cadena `v4.0.30319`.</span><span class="sxs-lookup"><span data-stu-id="7fd52-122">For the .NET Framework 4 and its point releases (the .NET Framework 4.5, 4.5.1, 4.5.2, and .NET Framework 4.6, 4.6.1, 4.6.2, and 4.7), it returns the string `v4.0.30319`.</span></span>

## <a name="see-also"></a><span data-ttu-id="7fd52-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fd52-123">See also</span></span>

- [<span data-ttu-id="7fd52-124">Compatibilidad de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="7fd52-124">Application compatibility</span></span>](application-compatibility.md)
