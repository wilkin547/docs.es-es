---
title: -link (Opciones del compilador de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- /l compiler option [C#]
- /link compiler option [C#]
- -l compiler option [C#]
- EmbedInteropTypes
- l compiler option [C#]
- embed interop types [COM Interop]
- -link compiler option [C#]
- link compiler option [C#]
ms.assetid: 00da70c6-9ea1-43c2-86f2-aa7f26c03475
ms.openlocfilehash: 00cfda489feb468c7e3c140ab63369b408b09152
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44183254"
---
# <a name="-link-c-compiler-options"></a><span data-ttu-id="d6a06-102">-link (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="d6a06-102">-link (C# Compiler Options)</span></span>
<span data-ttu-id="d6a06-103">Hace que el compilador facilite al proyecto que se está compilando información de tipos COM en los ensamblados especificados.</span><span class="sxs-lookup"><span data-stu-id="d6a06-103">Causes the compiler to make COM type information in the specified assemblies available to the project that you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6a06-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6a06-104">Syntax</span></span>  
  
```console  
-link:fileList  
// -or-  
-l:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="d6a06-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d6a06-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="d6a06-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d6a06-106">Required.</span></span> <span data-ttu-id="d6a06-107">Lista delimitada por comas de nombres de archivos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d6a06-107">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="d6a06-108">Si el nombre de archivo contiene un espacio, escríbalo entre comillas.</span><span class="sxs-lookup"><span data-stu-id="d6a06-108">If the file name contains a space, enclose the name in quotation marks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6a06-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6a06-109">Remarks</span></span>  
 <span data-ttu-id="d6a06-110">La opción `-link` permite implementar una aplicación que tiene información de tipo incrustada.</span><span class="sxs-lookup"><span data-stu-id="d6a06-110">The `-link` option enables you to deploy an application that has embedded type information.</span></span> <span data-ttu-id="d6a06-111">La aplicación puede usar los tipos de un ensamblado en tiempo de ejecución que implementan la información de tipo incrustada sin necesidad de una referencia al ensamblado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d6a06-111">The application can then use types in a runtime assembly that implement the embedded type information without requiring a reference to the runtime assembly.</span></span> <span data-ttu-id="d6a06-112">Si hay varias versiones del ensamblado en tiempo de ejecución publicadas, la aplicación que contiene la información de tipo incrustada puede trabajar con las distintas versiones sin tener que volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="d6a06-112">If various versions of the runtime assembly are published, the application that contains the embedded type information can work with the various versions without having to be recompiled.</span></span> <span data-ttu-id="d6a06-113">Para obtener un ejemplo, vea [Tutorial: Incrustar los tipos de los ensamblados administrados](../../programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="d6a06-113">For an example, see [Walkthrough: Embedding Types from Managed Assemblies](../../programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md).</span></span>  
  
 <span data-ttu-id="d6a06-114">La opción `-link` resulta de especial utilidad cuando se trabaja con la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="d6a06-114">Using the `-link` option is especially useful when you are working with COM interop.</span></span> <span data-ttu-id="d6a06-115">Puede incrustar tipos COM para que la aplicación ya no necesite un ensamblado de interoperabilidad primario (PIA) en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="d6a06-115">You can embed COM types so that your application no longer requires a primary interop assembly (PIA) on the target computer.</span></span> <span data-ttu-id="d6a06-116">La opción `-link` indica al compilador que incruste la información de tipo COM del ensamblado de interoperabilidad al que se hace referencia en el código compilado resultante.</span><span class="sxs-lookup"><span data-stu-id="d6a06-116">The `-link` option instructs the compiler to embed the COM type information from the referenced interop assembly into the resulting compiled code.</span></span> <span data-ttu-id="d6a06-117">El tipo COM se identifica mediante el valor de CLSID (GUID).</span><span class="sxs-lookup"><span data-stu-id="d6a06-117">The COM type is identified by the CLSID (GUID) value.</span></span> <span data-ttu-id="d6a06-118">Como resultado, la aplicación se puede ejecutar en un equipo de destino que tenga instalados los mismos tipos COM con los mismos valores de CLSID.</span><span class="sxs-lookup"><span data-stu-id="d6a06-118">As a result, your application can run on a target computer that has installed the same COM types with the same CLSID values.</span></span> <span data-ttu-id="d6a06-119">Las aplicaciones que automatizan Microsoft Office son un buen ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d6a06-119">Applications that automate Microsoft Office are a good example.</span></span> <span data-ttu-id="d6a06-120">Dado que las aplicaciones como Office suelen mantener el mismo valor de CLSID en las distintas versiones, la aplicación puede usar los tipos COM a los que se hace referencia siempre que .NET Framework 4 o posterior esté instalado en el equipo de destino y la aplicación emplee métodos, propiedades o eventos que estén incluidos en los tipos COM a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="d6a06-120">Because applications like Office usually keep the same CLSID value across different versions, your application can use the referenced COM types as long as .NET Framework 4 or later is installed on the target computer and your application uses methods, properties, or events that are included in the referenced COM types.</span></span>  
  
 <span data-ttu-id="d6a06-121">La opción `-link` incrusta únicamente interfaces, estructuras y delegados.</span><span class="sxs-lookup"><span data-stu-id="d6a06-121">The `-link` option embeds only interfaces, structures, and delegates.</span></span> <span data-ttu-id="d6a06-122">No se admite la incrustación de clases COM.</span><span class="sxs-lookup"><span data-stu-id="d6a06-122">Embedding COM classes is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6a06-123">Cuando se crea una instancia de un tipo COM incrustado en el código, hay que crear la instancia mediante la interfaz adecuada.</span><span class="sxs-lookup"><span data-stu-id="d6a06-123">When you create an instance of an embedded COM type in your code, you must create the instance by using the appropriate interface.</span></span> <span data-ttu-id="d6a06-124">Si se intenta crear una instancia de un tipo COM incrustado mediante la coclase, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="d6a06-124">Attempting to create an instance of an embedded COM type by using the CoClass causes an error.</span></span>  
  
 <span data-ttu-id="d6a06-125">Para establecer la opción `-link` en Visual Studio, agregue una referencia de ensamblado y establezca la propiedad `Embed Interop Types` en **true**.</span><span class="sxs-lookup"><span data-stu-id="d6a06-125">To set the `-link` option in Visual Studio, add an assembly reference and set the `Embed Interop Types` property to **true**.</span></span> <span data-ttu-id="d6a06-126">El valor predeterminado de la propiedad `Embed Interop Types` es **false**.</span><span class="sxs-lookup"><span data-stu-id="d6a06-126">The default for the `Embed Interop Types` property is **false**.</span></span>  
  
 <span data-ttu-id="d6a06-127">Si vincula a un ensamblado COM (ensamblado A) que a su vez hace referencia a otro ensamblado COM (ensamblado B), también debe vincular al ensamblado B si se cumple alguna de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="d6a06-127">If you link to a COM assembly (Assembly A) which itself references another COM assembly (Assembly B), you also have to link to Assembly B if either of the following is true:</span></span>  
  
-   <span data-ttu-id="d6a06-128">Un tipo del ensamblado A hereda de un tipo o implementa una interfaz del ensamblado B.</span><span class="sxs-lookup"><span data-stu-id="d6a06-128">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="d6a06-129">Se invoca a un campo, una propiedad, un evento o un método que tiene un tipo de parámetro o un tipo de valor devuelto del ensamblado B.</span><span class="sxs-lookup"><span data-stu-id="d6a06-129">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="d6a06-130">Al igual que la opción del compilador [-reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md), la opción del compilador `-link` usa el archivo de respuesta Csc.rsp, que hace referencia a ensamblados [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] usados con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="d6a06-130">Like the [-reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) compiler option, the `-link` compiler option uses the Csc.rsp response file, which references frequently used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies.</span></span> <span data-ttu-id="d6a06-131">Use la opción del compilador [-noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) si no quiere que el compilador emplee el archivo Csc.rsp.</span><span class="sxs-lookup"><span data-stu-id="d6a06-131">Use the [-noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) compiler option if you do not want the compiler to use the Csc.rsp file.</span></span>  
  
 <span data-ttu-id="d6a06-132">La forma abreviada de `-link` es `-l`.</span><span class="sxs-lookup"><span data-stu-id="d6a06-132">The short form of `-link` is `-l`.</span></span>  
  
## <a name="generics-and-embedded-types"></a><span data-ttu-id="d6a06-133">Tipos incrustados y genéricos</span><span class="sxs-lookup"><span data-stu-id="d6a06-133">Generics and Embedded Types</span></span>  
 <span data-ttu-id="d6a06-134">En las secciones siguientes se describen las limitaciones sobre el uso de tipos genéricos en aplicaciones que incrustan tipos de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="d6a06-134">The following sections describe the limitations on using generic types in applications that embed interop types.</span></span>  
  
### <a name="generic-interfaces"></a><span data-ttu-id="d6a06-135">Interfaces genéricas</span><span class="sxs-lookup"><span data-stu-id="d6a06-135">Generic Interfaces</span></span>  
 <span data-ttu-id="d6a06-136">No se puede usar interfaces genéricas que se incrusten desde un ensamblado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="d6a06-136">Generic interfaces that are embedded from an interop assembly cannot be used.</span></span> <span data-ttu-id="d6a06-137">Esta implementación se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d6a06-137">This is shown in the following example.</span></span>  
  
 [!code-csharp[VbLinkCompilerCS#1](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_1.cs)]  
  
### <a name="types-that-have-generic-parameters"></a><span data-ttu-id="d6a06-138">Tipos que tienen parámetros genéricos</span><span class="sxs-lookup"><span data-stu-id="d6a06-138">Types That Have Generic Parameters</span></span>  
 <span data-ttu-id="d6a06-139">Los tipos que tienen un parámetro genérico cuyo tipo se ha incrustado desde un ensamblado de interoperabilidad no se pueden usar si ese tipo pertenece a un ensamblado externo.</span><span class="sxs-lookup"><span data-stu-id="d6a06-139">Types that have a generic parameter whose type is embedded from an interop assembly cannot be used if that type is from an external assembly.</span></span> <span data-ttu-id="d6a06-140">Esta restricción no se aplica a las interfaces.</span><span class="sxs-lookup"><span data-stu-id="d6a06-140">This restriction does not apply to interfaces.</span></span> <span data-ttu-id="d6a06-141">Por ejemplo, considere la interfaz <xref:Microsoft.Office.Interop.Excel.Range> que se define en el ensamblado <xref:Microsoft.Office.Interop.Excel>.</span><span class="sxs-lookup"><span data-stu-id="d6a06-141">For example, consider the <xref:Microsoft.Office.Interop.Excel.Range> interface that is defined in the <xref:Microsoft.Office.Interop.Excel> assembly.</span></span> <span data-ttu-id="d6a06-142">Si una biblioteca inserta tipos de interoperabilidad desde el ensamblado <xref:Microsoft.Office.Interop.Excel> y expone un método que devuelve un tipo genérico que tiene un parámetro cuyo tipo es la interfaz <xref:Microsoft.Office.Interop.Excel.Range>, ese método debe devolver una interfaz genérica, como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d6a06-142">If a library embeds interop types from the <xref:Microsoft.Office.Interop.Excel> assembly and exposes a method that returns a generic type that has a parameter whose type is the <xref:Microsoft.Office.Interop.Excel.Range> interface, that method must return a generic interface, as shown in the following code example.</span></span>  
  
 [!code-csharp[VbLinkCompilerCS#2](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_2.cs)]  
[!code-csharp[VbLinkCompilerCS#3](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_3.cs)]  
[!code-csharp[VbLinkCompilerCS#4](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_4.cs)]  
  
 <span data-ttu-id="d6a06-143">En el ejemplo siguiente, el código de cliente puede llamar al método que devuelve la interfaz genérica <xref:System.Collections.IList> sin errores.</span><span class="sxs-lookup"><span data-stu-id="d6a06-143">In the following example, client code can call the method that returns the <xref:System.Collections.IList> generic interface without error.</span></span>  
  
 [!code-csharp[VbLinkCompilerCS#5](../../../csharp/language-reference/compiler-options/codesnippet/CSharp/link-compiler-option_5.cs)]  
  
## <a name="example"></a><span data-ttu-id="d6a06-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d6a06-144">Example</span></span>  
 <span data-ttu-id="d6a06-145">El código siguiente compila el archivo de origen `OfficeApp.cs` y hace referencia a ensamblados de `COMData1.dll` y `COMData2.dll` para generar `OfficeApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="d6a06-145">The following code compiles source file `OfficeApp.cs` and reference assemblies from `COMData1.dll` and `COMData2.dll` to produce `OfficeApp.exe`.</span></span>  
  
```csharp  
csc -link:COMData1.dll,COMData2.dll -out:OfficeApp.exe OfficeApp.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6a06-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6a06-146">See Also</span></span>

- [<span data-ttu-id="d6a06-147">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="d6a06-147">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="d6a06-148">Tutorial: Incrustación de los tipos de los ensamblados administrados</span><span class="sxs-lookup"><span data-stu-id="d6a06-148">Walkthrough: Embedding Types from Managed Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)  
- [<span data-ttu-id="d6a06-149">-reference (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="d6a06-149">-reference (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)  
- [<span data-ttu-id="d6a06-150">-noconfig (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="d6a06-150">-noconfig (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)  
- [<span data-ttu-id="d6a06-151">Compilar la línea de comandos con csc.exe</span><span class="sxs-lookup"><span data-stu-id="d6a06-151">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
- [<span data-ttu-id="d6a06-152">Información general sobre interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="d6a06-152">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)
