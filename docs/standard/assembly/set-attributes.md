---
title: Establecimiento de atributos de ensamblado
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], attributes
- assembly binding, attributes
- assembly manifest, attributes
ms.assetid: 36a98a81-b5b5-4c19-912a-11f91eff7f4e
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 0e4e2e595ed4f95511bd23ab0ed00139f71b2c8b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73740473"
---
# <a name="set-assembly-attributes"></a><span data-ttu-id="dfd31-102">Establecimiento de atributos de ensamblado</span><span class="sxs-lookup"><span data-stu-id="dfd31-102">Set assembly attributes</span></span>

<span data-ttu-id="dfd31-103">Los atributos de ensamblado son valores que proporcionan información sobre un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dfd31-103">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="dfd31-104">Los atributos se dividen en los siguientes conjuntos de información:</span><span class="sxs-lookup"><span data-stu-id="dfd31-104">The attributes are divided into the following sets of information:</span></span>

- <span data-ttu-id="dfd31-105">Atributos de identidad del ensamblado</span><span class="sxs-lookup"><span data-stu-id="dfd31-105">Assembly identity attributes</span></span>

- <span data-ttu-id="dfd31-106">Atributos informativos</span><span class="sxs-lookup"><span data-stu-id="dfd31-106">Informational attributes</span></span>

- <span data-ttu-id="dfd31-107">Atributos de manifiesto del ensamblado</span><span class="sxs-lookup"><span data-stu-id="dfd31-107">Assembly manifest attributes</span></span>

- <span data-ttu-id="dfd31-108">Atributos de nombre seguro</span><span class="sxs-lookup"><span data-stu-id="dfd31-108">Strong name attributes</span></span>

## <a name="assembly-identity-attributes"></a><span data-ttu-id="dfd31-109">Atributos de identidad del ensamblado</span><span class="sxs-lookup"><span data-stu-id="dfd31-109">Assembly identity attributes</span></span>

<span data-ttu-id="dfd31-110">Tres atributos, junto con un nombre seguro (si procede), determinan la identidad de un ensamblado: nombre, versión y referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="dfd31-110">Three attributes, together with a strong name (if applicable), determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="dfd31-111">Estos atributos forman el nombre completo del ensamblado y son necesarios cuando se hace referencia el ensamblado en el código.</span><span class="sxs-lookup"><span data-stu-id="dfd31-111">These attributes form the full name of the assembly and are required when referencing the assembly in code.</span></span> <span data-ttu-id="dfd31-112">Puede usar atributos para establecer la versión y la referencia cultural de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dfd31-112">You can use attributes to set an assembly's version and culture.</span></span> <span data-ttu-id="dfd31-113">El compilador o el [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) establecen el valor de nombre cuando se crea el ensamblado, basándose en el archivo que contiene el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dfd31-113">The compiler or the [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) sets the name value when the assembly is created, based on the file containing the assembly manifest.</span></span>

<span data-ttu-id="dfd31-114">En la tabla siguiente se describen los atributos de versión y de referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="dfd31-114">The following table describes the version and culture attributes.</span></span>

|<span data-ttu-id="dfd31-115">Atributo de identidad del ensamblado</span><span class="sxs-lookup"><span data-stu-id="dfd31-115">Assembly identity attribute</span></span>|<span data-ttu-id="dfd31-116">Description</span><span class="sxs-lookup"><span data-stu-id="dfd31-116">Description</span></span>|
|---------------------------------|-----------------|
|<xref:System.Reflection.AssemblyCultureAttribute>|<span data-ttu-id="dfd31-117">Campo enumerado que indica la referencia cultural que admite el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dfd31-117">Enumerated field indicating the culture that the assembly supports.</span></span> <span data-ttu-id="dfd31-118">Un ensamblado también puede especificar independencia de la referencia cultural, lo que indica que contiene los recursos para la referencia cultural predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dfd31-118">An assembly can also specify culture independence, indicating that it contains the resources for the default culture.</span></span> <span data-ttu-id="dfd31-119">**Nota:** El tiempo de ejecución trata cualquier ensamblado que no tenga el atributo de referencia cultural establecido en NULL como un ensamblado satélite.</span><span class="sxs-lookup"><span data-stu-id="dfd31-119">**Note:**  The runtime treats any assembly that does not have the culture attribute set to null as a satellite assembly.</span></span> <span data-ttu-id="dfd31-120">Estos ensamblados están sujetos a las reglas de enlace de ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="dfd31-120">Such assemblies are subject to satellite assembly binding rules.</span></span> <span data-ttu-id="dfd31-121">Para más información, consulte [Cómo el motor en tiempo de ejecución ubica ensamblados](../../framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="dfd31-121">For more information, see [How the runtime locates assemblies](../../framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>|
|<xref:System.Reflection.AssemblyFlagsAttribute>|<span data-ttu-id="dfd31-122">Valor que establece atributos de ensamblado, como por ejemplo, si se puede ejecutar el ensamblado en paralelo.</span><span class="sxs-lookup"><span data-stu-id="dfd31-122">Value that sets assembly attributes, such as whether the assembly can be run side by side.</span></span>|
|<xref:System.Reflection.AssemblyVersionAttribute>|<span data-ttu-id="dfd31-123">Valor numérico con el formato *versión_principal*.*versión_secundaria*.*compilación*.*revisión* (por ejemplo, 2.4.0.0).</span><span class="sxs-lookup"><span data-stu-id="dfd31-123">Numeric value in the format *major*.*minor*.*build*.*revision* (for example, 2.4.0.0).</span></span> <span data-ttu-id="dfd31-124">Common Language Runtime usa este valor para realizar operaciones de enlace en ensamblados con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="dfd31-124">The common language runtime uses this value to perform binding operations in strong-named assemblies.</span></span> <span data-ttu-id="dfd31-125">**Nota:** Si el atributo <xref:System.Reflection.AssemblyInformationalVersionAttribute> no se aplica a un ensamblado, el número de versión que especifica el atributo <xref:System.Reflection.AssemblyVersionAttribute> lo usan las propiedades <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> y <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dfd31-125">**Note:**  If the <xref:System.Reflection.AssemblyInformationalVersionAttribute> attribute is not applied to an assembly, the version number specified by the <xref:System.Reflection.AssemblyVersionAttribute> attribute is used by the <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType>, and <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> properties.</span></span>|

<span data-ttu-id="dfd31-126">En el ejemplo de código siguiente se muestra cómo aplicar los atributos de versión y referencia cultural a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dfd31-126">The following code example shows how to apply the version and culture attributes to an assembly.</span></span>

```cpp
// Set version number for the assembly.
[assembly:AssemblyVersionAttribute("4.3.2.1")];
// Set culture as German.
[assembly:AssemblyCultureAttribute("de")];
```

```csharp
// Set version number for the assembly.
[assembly:AssemblyVersionAttribute("4.3.2.1")]
// Set culture as German.
[assembly:AssemblyCultureAttribute("de")]
```

```vb
' Set version number for the assembly.
<Assembly:AssemblyVersionAttribute("4.3.2.1")>
' Set culture as German.
<Assembly:AssemblyCultureAttribute("de")>
```

## <a name="informational-attributes"></a><span data-ttu-id="dfd31-127">Atributos informativos</span><span class="sxs-lookup"><span data-stu-id="dfd31-127">Informational attributes</span></span>

<span data-ttu-id="dfd31-128">Puede utilizar atributos informativos para proporcionar información adicional de la compañía o de producto para un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dfd31-128">You can use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="dfd31-129">En la tabla siguiente se describen los atributos informativos que se pueden aplicar a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dfd31-129">The following table describes the informational attributes you can apply to an assembly.</span></span>

|<span data-ttu-id="dfd31-130">Atributo informativo</span><span class="sxs-lookup"><span data-stu-id="dfd31-130">Informational attribute</span></span>|<span data-ttu-id="dfd31-131">Description</span><span class="sxs-lookup"><span data-stu-id="dfd31-131">Description</span></span>|
|-----------------------------|-----------------|
|<xref:System.Reflection.AssemblyCompanyAttribute>|<span data-ttu-id="dfd31-132">Valor de cadena que especifica un nombre de compañía.</span><span class="sxs-lookup"><span data-stu-id="dfd31-132">String value specifying a company name.</span></span>|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|<span data-ttu-id="dfd31-133">Valor de cadena que especifica información de copyright.</span><span class="sxs-lookup"><span data-stu-id="dfd31-133">String value specifying copyright information.</span></span>|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|<span data-ttu-id="dfd31-134">Valor de cadena que especifica el número de versión del archivo Win32.</span><span class="sxs-lookup"><span data-stu-id="dfd31-134">String value specifying the Win32 file version number.</span></span> <span data-ttu-id="dfd31-135">Normalmente el valor predeterminado es la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dfd31-135">This normally defaults to the assembly version.</span></span>|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|<span data-ttu-id="dfd31-136">Valor de cadena que especifica la información de versión que Common Language Runtime no usa, como por ejemplo un número de versión del producto completo.</span><span class="sxs-lookup"><span data-stu-id="dfd31-136">String value specifying version information that is not used by the common language runtime, such as a full product version number.</span></span> <span data-ttu-id="dfd31-137">**Nota:** Si este atributo se aplica a un ensamblado, se puede obtener la cadena que especifica en tiempo de ejecución mediante la propiedad <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dfd31-137">**Note:**  If this attribute is applied to an assembly, the string it specifies can be obtained at run time by using the <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="dfd31-138">La cadena también se utiliza en la clave del Registro y la ruta de acceso que proporcionan las propiedades <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> y <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="dfd31-138">The string is also used in the path and registry key provided by the <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> properties.</span></span>|
|<xref:System.Reflection.AssemblyProductAttribute>|<span data-ttu-id="dfd31-139">Valor de cadena que especifica la información del producto.</span><span class="sxs-lookup"><span data-stu-id="dfd31-139">String value specifying product information.</span></span>|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|<span data-ttu-id="dfd31-140">Valor de cadena que especifica la información de marca comercial.</span><span class="sxs-lookup"><span data-stu-id="dfd31-140">String value specifying trademark information.</span></span>|

<span data-ttu-id="dfd31-141">Estos atributos pueden aparecer en la página Propiedades de Windows del ensamblado o se pueden reemplazar con la opción del compilador **/win32res** para especificar su propio archivo de recursos de Win32.</span><span class="sxs-lookup"><span data-stu-id="dfd31-141">These attributes can appear on the Windows Properties page of the assembly, or they can be overridden using the **/win32res** compiler option to specify your own Win32 resource file.</span></span>

## <a name="assembly-manifest-attributes"></a><span data-ttu-id="dfd31-142">Atributos de manifiesto del ensamblado</span><span class="sxs-lookup"><span data-stu-id="dfd31-142">Assembly manifest attributes</span></span>

<span data-ttu-id="dfd31-143">Puede utilizar atributos de manifiesto del ensamblado para proporcionar información en el manifiesto del ensamblado, incluidos el título, la descripción, el alias predeterminado y la configuración.</span><span class="sxs-lookup"><span data-stu-id="dfd31-143">You can use assembly manifest attributes to provide information in the assembly manifest, including title, description, the default alias, and configuration.</span></span> <span data-ttu-id="dfd31-144">En la tabla siguiente se describen los atributos de manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dfd31-144">The following table describes the assembly manifest attributes.</span></span>

|<span data-ttu-id="dfd31-145">Atributo de manifiesto del ensamblado</span><span class="sxs-lookup"><span data-stu-id="dfd31-145">Assembly manifest attribute</span></span>|<span data-ttu-id="dfd31-146">Description</span><span class="sxs-lookup"><span data-stu-id="dfd31-146">Description</span></span>|
|---------------------------------|-----------------|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|<span data-ttu-id="dfd31-147">Valor de cadena que indica la configuración del ensamblado, como Retail o Debug.</span><span class="sxs-lookup"><span data-stu-id="dfd31-147">String value indicating the configuration of the assembly, such as Retail or Debug.</span></span> <span data-ttu-id="dfd31-148">El tiempo de ejecución no utiliza este valor.</span><span class="sxs-lookup"><span data-stu-id="dfd31-148">The runtime does not use this value.</span></span>|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|<span data-ttu-id="dfd31-149">Valor de cadena que especifica un alias predeterminado que utilizarán los ensamblados de referencia.</span><span class="sxs-lookup"><span data-stu-id="dfd31-149">String value specifying a default alias to be used by referencing assemblies.</span></span> <span data-ttu-id="dfd31-150">Este valor proporciona un nombre descriptivo cuando el nombre del ensamblado no es descriptivo por sí solo (por ejemplo, un valor GUID).</span><span class="sxs-lookup"><span data-stu-id="dfd31-150">This value provides a friendly name when the name of the assembly itself is not friendly (such as a GUID value).</span></span> <span data-ttu-id="dfd31-151">Este valor también puede utilizarse como una forma abreviada del nombre completo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dfd31-151">This value can also be used as a short form of the full assembly name.</span></span>|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|<span data-ttu-id="dfd31-152">Valor de cadena que especifica una breve descripción que resume la naturaleza y el propósito del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dfd31-152">String value specifying a short description that summarizes the nature and purpose of the assembly.</span></span>|
|<xref:System.Reflection.AssemblyTitleAttribute>|<span data-ttu-id="dfd31-153">Valor de cadena que especifica un nombre descriptivo para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dfd31-153">String value specifying a friendly name for the assembly.</span></span> <span data-ttu-id="dfd31-154">Por ejemplo, un ensamblado denominado *comdlg* puede tener el título “Microsoft Common Dialog Control”.</span><span class="sxs-lookup"><span data-stu-id="dfd31-154">For example, an assembly named *comdlg* might have the title Microsoft Common Dialog Control.</span></span>|

## <a name="strong-name-attributes"></a><span data-ttu-id="dfd31-155">Atributos de nombre seguro</span><span class="sxs-lookup"><span data-stu-id="dfd31-155">Strong name attributes</span></span>

<span data-ttu-id="dfd31-156">Puede utilizar atributos de nombre seguro para establecer un nombre seguro para un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dfd31-156">You can use strong name attributes to set a strong name for an assembly.</span></span> <span data-ttu-id="dfd31-157">En la tabla siguiente se describen los atributos de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="dfd31-157">The following table describes the strong name attributes.</span></span>

|<span data-ttu-id="dfd31-158">Atributos de nombre seguro</span><span class="sxs-lookup"><span data-stu-id="dfd31-158">Strong name attribute</span></span>|<span data-ttu-id="dfd31-159">Description</span><span class="sxs-lookup"><span data-stu-id="dfd31-159">Description</span></span>|
|----------------------------|-----------------|
|<xref:System.Reflection.AssemblyDelaySignAttribute>|<span data-ttu-id="dfd31-160">Valor booleano que indica que se está usando la firma retardada.</span><span class="sxs-lookup"><span data-stu-id="dfd31-160">Boolean value indicating that delay signing is being used.</span></span>|
|<xref:System.Reflection.AssemblyKeyFileAttribute>|<span data-ttu-id="dfd31-161">Valor de cadena que indica el nombre del archivo que contiene la clave pública (si se usa la firma retardada) o las claves públicas y privadas que se pasan como un parámetro al constructor de este atributo.</span><span class="sxs-lookup"><span data-stu-id="dfd31-161">String value indicating the name of the file that contains either the public key (if using delay signing) or both the public and private keys passed as a parameter to the constructor of this attribute.</span></span> <span data-ttu-id="dfd31-162">Tenga en cuenta que el nombre de archivo es relativo a la ruta de acceso del archivo de salida ( *.exe* o *.dll*), no a la ruta de acceso del archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="dfd31-162">Note that the file name is relative to the output file path (the *.exe* or *.dll*), not the source file path.</span></span>|
|<xref:System.Reflection.AssemblyKeyNameAttribute>|<span data-ttu-id="dfd31-163">Indica el contenedor de claves que contiene el par de claves que se pasa como parámetro al constructor de este atributo.</span><span class="sxs-lookup"><span data-stu-id="dfd31-163">Indicates the key container that contains the key pair passed as a parameter to the constructor of this attribute.</span></span>|

<span data-ttu-id="dfd31-164">En el ejemplo de código siguiente, se muestran los atributos que se aplicarán cuando se use la firma retardada para crear un ensamblado con nombre seguro con un archivo de clave pública denominado *myKey.snk*.</span><span class="sxs-lookup"><span data-stu-id="dfd31-164">The following code example shows the attributes to apply when using delay signing to create a strong-named assembly with a public key file called *myKey.snk*.</span></span>

```cpp
[assembly:AssemblyKeyFileAttribute("myKey.snk")];
[assembly:AssemblyDelaySignAttribute(true)];
```

```csharp
[assembly:AssemblyKeyFileAttribute("myKey.snk")]
[assembly:AssemblyDelaySignAttribute(true)]
```

```vb
<Assembly:AssemblyKeyFileAttribute("myKey.snk")>
<Assembly:AssemblyDelaySignAttribute(True)>
```

## <a name="see-also"></a><span data-ttu-id="dfd31-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfd31-165">See also</span></span>

- [<span data-ttu-id="dfd31-166">Creación de ensamblados</span><span class="sxs-lookup"><span data-stu-id="dfd31-166">Create assemblies</span></span>](create.md)
