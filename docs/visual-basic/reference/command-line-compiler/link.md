---
title: -link (Visual Basic)
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- l compiler option [Visual Basic]
- EmbedInteropTypes
- embed interop types [COM Interop]
- -link compiler option [Visual Basic]
- /link compiler option [Visual Basic]
- link compiler option [Visual Basic]
- -l compiler option [Visual Basic]
- /l compiler option [Visual Basic]
ms.assetid: 1885f24a-86f5-486c-a064-9fb7e455ccec
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4699e3adfd83a35ee81a5c8838e300adf6ecf667
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="-link-visual-basic"></a><span data-ttu-id="17c01-102">-link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17c01-102">-link (Visual Basic)</span></span>
<span data-ttu-id="17c01-103">Hace que el compilador facilite al proyecto que se está compilando información de tipos COM en los ensamblados especificados.</span><span class="sxs-lookup"><span data-stu-id="17c01-103">Causes the compiler to make COM type information in the specified assemblies available to the project that you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17c01-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17c01-104">Syntax</span></span>  
  
```  
-link:fileList  
' -or-  
-l:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="17c01-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="17c01-105">Arguments</span></span>  
  
|<span data-ttu-id="17c01-106">Término</span><span class="sxs-lookup"><span data-stu-id="17c01-106">Term</span></span>|<span data-ttu-id="17c01-107">Definición</span><span class="sxs-lookup"><span data-stu-id="17c01-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="17c01-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="17c01-108">Required.</span></span> <span data-ttu-id="17c01-109">Lista delimitada por comas de nombres de archivos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="17c01-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="17c01-110">Si el nombre de archivo contiene un espacio, escríbalo entre comillas.</span><span class="sxs-lookup"><span data-stu-id="17c01-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17c01-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="17c01-111">Remarks</span></span>  
 <span data-ttu-id="17c01-112">La opción `-link` permite implementar una aplicación que tiene información de tipo incrustada.</span><span class="sxs-lookup"><span data-stu-id="17c01-112">The `-link` option enables you to deploy an application that has embedded type information.</span></span> <span data-ttu-id="17c01-113">La aplicación puede usar los tipos de un ensamblado en tiempo de ejecución que implementan la información de tipo incrustada sin necesidad de una referencia al ensamblado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="17c01-113">The application can then use types in a runtime assembly that implement the embedded type information without requiring a reference to the runtime assembly.</span></span> <span data-ttu-id="17c01-114">Si hay varias versiones del ensamblado en tiempo de ejecución publicadas, la aplicación que contiene la información de tipo incrustada puede trabajar con las distintas versiones sin tener que volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="17c01-114">If various versions of the runtime assembly are published, the application that contains the embedded type information can work with the various versions without having to be recompiled.</span></span> <span data-ttu-id="17c01-115">Para obtener un ejemplo, vea [Tutorial: Incrustar los tipos de los ensamblados administrados](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span><span class="sxs-lookup"><span data-stu-id="17c01-115">For an example, see [Walkthrough: Embedding Types from Managed Assemblies](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span></span>  
  
 <span data-ttu-id="17c01-116">La opción `-link` resulta de especial utilidad cuando se trabaja con la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="17c01-116">Using the `-link` option is especially useful when you are working with COM interop.</span></span> <span data-ttu-id="17c01-117">Puede incrustar tipos COM para que la aplicación ya no necesite un ensamblado de interoperabilidad primario (PIA) en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="17c01-117">You can embed COM types so that your application no longer requires a primary interop assembly (PIA) on the target computer.</span></span> <span data-ttu-id="17c01-118">La opción `-link` indica al compilador que incruste la información de tipo COM del ensamblado de interoperabilidad al que se hace referencia en el código compilado resultante.</span><span class="sxs-lookup"><span data-stu-id="17c01-118">The `-link` option instructs the compiler to embed the COM type information from the referenced interop assembly into the resulting compiled code.</span></span> <span data-ttu-id="17c01-119">El tipo COM se identifica mediante el valor de CLSID (GUID).</span><span class="sxs-lookup"><span data-stu-id="17c01-119">The COM type is identified by the CLSID (GUID) value.</span></span> <span data-ttu-id="17c01-120">Como resultado, la aplicación se puede ejecutar en un equipo de destino que tenga instalados los mismos tipos COM con los mismos valores de CLSID.</span><span class="sxs-lookup"><span data-stu-id="17c01-120">As a result, your application can run on a target computer that has installed the same COM types with the same CLSID values.</span></span> <span data-ttu-id="17c01-121">Las aplicaciones que automatizan Microsoft Office son un buen ejemplo.</span><span class="sxs-lookup"><span data-stu-id="17c01-121">Applications that automate Microsoft Office are a good example.</span></span> <span data-ttu-id="17c01-122">Dado que las aplicaciones como Office suelen mantener el mismo valor de CLSID en las distintas versiones, la aplicación puede usar los tipos COM a los que se hace referencia siempre que .NET Framework 4 o posterior esté instalado en el equipo de destino y la aplicación emplee métodos, propiedades o eventos que estén incluidos en los tipos COM a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="17c01-122">Because applications like Office usually keep the same CLSID value across different versions, your application can use the referenced COM types as long as .NET Framework 4 or later is installed on the target computer and your application uses methods, properties, or events that are included in the referenced COM types.</span></span>  
  
 <span data-ttu-id="17c01-123">La opción `-link` incrusta únicamente interfaces, estructuras y delegados.</span><span class="sxs-lookup"><span data-stu-id="17c01-123">The `-link` option embeds only interfaces, structures, and delegates.</span></span> <span data-ttu-id="17c01-124">No se admite la incrustación de clases COM.</span><span class="sxs-lookup"><span data-stu-id="17c01-124">Embedding COM classes is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17c01-125">Cuando se crea una instancia de un tipo COM incrustado en el código, hay que crear la instancia mediante la interfaz adecuada.</span><span class="sxs-lookup"><span data-stu-id="17c01-125">When you create an instance of an embedded COM type in your code, you must create the instance by using the appropriate interface.</span></span> <span data-ttu-id="17c01-126">Si se intenta crear una instancia de un tipo COM incrustado mediante la coclase, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="17c01-126">Attempting to create an instance of an embedded COM type by using the CoClass causes an error.</span></span>  
  
 <span data-ttu-id="17c01-127">Para establecer el `-link` opción en Visual Studio, agregue una referencia de ensamblado y establezca el `Embed Interop Types` propiedad **true**.</span><span class="sxs-lookup"><span data-stu-id="17c01-127">To set the `-link` option in Visual Studio, add an assembly reference and set the `Embed Interop Types` property to **true**.</span></span> <span data-ttu-id="17c01-128">El valor predeterminado de la propiedad `Embed Interop Types` es **false**.</span><span class="sxs-lookup"><span data-stu-id="17c01-128">The default for the `Embed Interop Types` property is **false**.</span></span>  
  
 <span data-ttu-id="17c01-129">Si vincula a un ensamblado COM (ensamblado A) que a su vez hace referencia a otro ensamblado COM (ensamblado B), también debe vincular al ensamblado B si se cumple alguna de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="17c01-129">If you link to a COM assembly (Assembly A) which itself references another COM assembly (Assembly B), you also have to link to Assembly B if either of the following is true:</span></span>  
  
-   <span data-ttu-id="17c01-130">Un tipo del ensamblado A hereda de un tipo o implementa una interfaz del ensamblado B.</span><span class="sxs-lookup"><span data-stu-id="17c01-130">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="17c01-131">Se invoca a un campo, una propiedad, un evento o un método que tiene un tipo de parámetro o un tipo de valor devuelto del ensamblado B.</span><span class="sxs-lookup"><span data-stu-id="17c01-131">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="17c01-132">Use [- libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) para especificar el directorio en el que se encuentran una o varias de las referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="17c01-132">Use [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="17c01-133">Al igual que el [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) opción del compilador, el `-link` opción del compilador usa el archivo de respuesta Vbc.rsp, que se utilizan con frecuencia las referencias [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ensamblados.</span><span class="sxs-lookup"><span data-stu-id="17c01-133">Like the [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) compiler option, the `-link` compiler option uses the Vbc.rsp response file, which references frequently used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies.</span></span> <span data-ttu-id="17c01-134">Utilice la [- noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) opción del compilador si no desea que el compilador que use el archivo Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="17c01-134">Use the [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) compiler option if you do not want the compiler to use the Vbc.rsp file.</span></span>  
  
 <span data-ttu-id="17c01-135">La forma abreviada de `-link` es `-l`.</span><span class="sxs-lookup"><span data-stu-id="17c01-135">The short form of `-link` is `-l`.</span></span>  
  
## <a name="generics-and-embedded-types"></a><span data-ttu-id="17c01-136">Tipos incrustados y genéricos</span><span class="sxs-lookup"><span data-stu-id="17c01-136">Generics and Embedded Types</span></span>  
 <span data-ttu-id="17c01-137">En las secciones siguientes se describen las limitaciones sobre el uso de tipos genéricos en aplicaciones que incrustan tipos de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="17c01-137">The following sections describe the limitations on using generic types in applications that embed interop types.</span></span>  
  
### <a name="generic-interfaces"></a><span data-ttu-id="17c01-138">Interfaces genéricas</span><span class="sxs-lookup"><span data-stu-id="17c01-138">Generic Interfaces</span></span>  
 <span data-ttu-id="17c01-139">No se puede usar interfaces genéricas que se incrusten desde un ensamblado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="17c01-139">Generic interfaces that are embedded from an interop assembly cannot be used.</span></span> <span data-ttu-id="17c01-140">Esta implementación se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="17c01-140">This is shown in the following example.</span></span>  
  
 [!code-vb[VbLinkCompiler#1](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_1.vb)]  
  
### <a name="types-that-have-generic-parameters"></a><span data-ttu-id="17c01-141">Tipos que tienen parámetros genéricos</span><span class="sxs-lookup"><span data-stu-id="17c01-141">Types That Have Generic Parameters</span></span>  
 <span data-ttu-id="17c01-142">Los tipos que tienen un parámetro genérico cuyo tipo se ha incrustado desde un ensamblado de interoperabilidad no se pueden usar si ese tipo pertenece a un ensamblado externo.</span><span class="sxs-lookup"><span data-stu-id="17c01-142">Types that have a generic parameter whose type is embedded from an interop assembly cannot be used if that type is from an external assembly.</span></span> <span data-ttu-id="17c01-143">Esta restricción no se aplica a las interfaces.</span><span class="sxs-lookup"><span data-stu-id="17c01-143">This restriction does not apply to interfaces.</span></span> <span data-ttu-id="17c01-144">Por ejemplo, considere la interfaz <xref:Microsoft.Office.Interop.Excel.Range> que se define en el ensamblado <xref:Microsoft.Office.Interop.Excel>.</span><span class="sxs-lookup"><span data-stu-id="17c01-144">For example, consider the <xref:Microsoft.Office.Interop.Excel.Range> interface that is defined in the <xref:Microsoft.Office.Interop.Excel> assembly.</span></span> <span data-ttu-id="17c01-145">Si una biblioteca inserta tipos de interoperabilidad desde el ensamblado <xref:Microsoft.Office.Interop.Excel> y expone un método que devuelve un tipo genérico que tiene un parámetro cuyo tipo es la interfaz <xref:Microsoft.Office.Interop.Excel.Range>, ese método debe devolver una interfaz genérica, como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="17c01-145">If a library embeds interop types from the <xref:Microsoft.Office.Interop.Excel> assembly and exposes a method that returns a generic type that has a parameter whose type is the <xref:Microsoft.Office.Interop.Excel.Range> interface, that method must return a generic interface, as shown in the following code example.</span></span>  
  
 [!code-vb[VbLinkCompiler#2](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_2.vb)]  
[!code-vb[VbLinkCompiler#3](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_3.vb)]  
[!code-vb[VbLinkCompiler#4](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_4.vb)]  
  
 <span data-ttu-id="17c01-146">En el ejemplo siguiente, el código de cliente puede llamar al método que devuelve la interfaz genérica <xref:System.Collections.IList> sin errores.</span><span class="sxs-lookup"><span data-stu-id="17c01-146">In the following example, client code can call the method that returns the <xref:System.Collections.IList> generic interface without error.</span></span>  
  
 [!code-vb[VbLinkCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_5.vb)]  
  
## <a name="example"></a><span data-ttu-id="17c01-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17c01-147">Example</span></span>  
 <span data-ttu-id="17c01-148">La línea de comandos siguiente compila el archivo de código fuente `OfficeApp.vb` y hacer referencia a ensamblados de `COMData1.dll` y `COMData2.dll` para generar `OfficeApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="17c01-148">The following command line compiles source file `OfficeApp.vb` and reference assemblies from `COMData1.dll` and `COMData2.dll` to produce `OfficeApp.exe`.</span></span>  
  
```console  
vbc -link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="17c01-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="17c01-149">See Also</span></span>  
 [<span data-ttu-id="17c01-150">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="17c01-150">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="17c01-151">Tutorial: Incrustación de los tipos de los ensamblados administrados</span><span class="sxs-lookup"><span data-stu-id="17c01-151">Walkthrough: Embedding Types from Managed Assemblies</span></span>](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)  
 [<span data-ttu-id="17c01-152">-referencia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17c01-152">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [<span data-ttu-id="17c01-153">-noconfig</span><span class="sxs-lookup"><span data-stu-id="17c01-153">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [<span data-ttu-id="17c01-154">-libpath</span><span class="sxs-lookup"><span data-stu-id="17c01-154">-libpath</span></span>](../../../visual-basic/reference/command-line-compiler/libpath.md)  
 [<span data-ttu-id="17c01-155">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="17c01-155">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="17c01-156">Introducción a la interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="17c01-156">Introduction to COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)
