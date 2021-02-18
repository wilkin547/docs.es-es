---
description: Mas información sobre -link (Visual Basic)
title: -link
ms.date: 03/10/2018
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
ms.openlocfilehash: 31d98d2c0fb0cbd8e8baff82869501a7ff0ea270
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475141"
---
# <a name="-link-visual-basic"></a><span data-ttu-id="90e5e-103">-link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90e5e-103">-link (Visual Basic)</span></span>

<span data-ttu-id="90e5e-104">Hace que el compilador facilite al proyecto que se está compilando información de tipos COM en los ensamblados especificados.</span><span class="sxs-lookup"><span data-stu-id="90e5e-104">Causes the compiler to make COM type information in the specified assemblies available to the project that you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90e5e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90e5e-105">Syntax</span></span>  
  
```console  
-link:fileList  
```

<span data-ttu-id="90e5e-106">o</span><span class="sxs-lookup"><span data-stu-id="90e5e-106">or</span></span>  

```console
-l:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="90e5e-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="90e5e-107">Arguments</span></span>  
  
|<span data-ttu-id="90e5e-108">Término</span><span class="sxs-lookup"><span data-stu-id="90e5e-108">Term</span></span>|<span data-ttu-id="90e5e-109">Definición</span><span class="sxs-lookup"><span data-stu-id="90e5e-109">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="90e5e-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="90e5e-110">Required.</span></span> <span data-ttu-id="90e5e-111">Lista delimitada por comas de nombres de archivos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="90e5e-111">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="90e5e-112">Si el nombre de archivo contiene un espacio, escríbalo entre comillas.</span><span class="sxs-lookup"><span data-stu-id="90e5e-112">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90e5e-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="90e5e-113">Remarks</span></span>  

 <span data-ttu-id="90e5e-114">La opción `-link` permite implementar una aplicación que tiene información de tipo incrustada.</span><span class="sxs-lookup"><span data-stu-id="90e5e-114">The `-link` option enables you to deploy an application that has embedded type information.</span></span> <span data-ttu-id="90e5e-115">La aplicación puede usar los tipos de un ensamblado en tiempo de ejecución que implementan la información de tipo incrustada sin necesidad de una referencia al ensamblado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="90e5e-115">The application can then use types in a runtime assembly that implement the embedded type information without requiring a reference to the runtime assembly.</span></span> <span data-ttu-id="90e5e-116">Si hay varias versiones del ensamblado en tiempo de ejecución publicadas, la aplicación que contiene la información de tipo incrustada puede trabajar con las distintas versiones sin tener que volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="90e5e-116">If various versions of the runtime assembly are published, the application that contains the embedded type information can work with the various versions without having to be recompiled.</span></span> <span data-ttu-id="90e5e-117">Para obtener un ejemplo, vea [Tutorial: Insertar los tipos de los ensamblados administrados](../../../standard/assembly/embed-types-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="90e5e-117">For an example, see [Walkthrough: Embedding Types from Managed Assemblies](../../../standard/assembly/embed-types-visual-studio.md).</span></span>  
  
 <span data-ttu-id="90e5e-118">La opción `-link` resulta de especial utilidad cuando se trabaja con la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="90e5e-118">Using the `-link` option is especially useful when you are working with COM interop.</span></span> <span data-ttu-id="90e5e-119">Puede incrustar tipos COM para que la aplicación ya no necesite un ensamblado de interoperabilidad primario (PIA) en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="90e5e-119">You can embed COM types so that your application no longer requires a primary interop assembly (PIA) on the target computer.</span></span> <span data-ttu-id="90e5e-120">La opción `-link` indica al compilador que incruste la información de tipo COM del ensamblado de interoperabilidad al que se hace referencia en el código compilado resultante.</span><span class="sxs-lookup"><span data-stu-id="90e5e-120">The `-link` option instructs the compiler to embed the COM type information from the referenced interop assembly into the resulting compiled code.</span></span> <span data-ttu-id="90e5e-121">El tipo COM se identifica mediante el valor de CLSID (GUID).</span><span class="sxs-lookup"><span data-stu-id="90e5e-121">The COM type is identified by the CLSID (GUID) value.</span></span> <span data-ttu-id="90e5e-122">Como resultado, la aplicación se puede ejecutar en un equipo de destino que tenga instalados los mismos tipos COM con los mismos valores de CLSID.</span><span class="sxs-lookup"><span data-stu-id="90e5e-122">As a result, your application can run on a target computer that has installed the same COM types with the same CLSID values.</span></span> <span data-ttu-id="90e5e-123">Las aplicaciones que automatizan Microsoft Office son un buen ejemplo.</span><span class="sxs-lookup"><span data-stu-id="90e5e-123">Applications that automate Microsoft Office are a good example.</span></span> <span data-ttu-id="90e5e-124">Dado que las aplicaciones como Office suelen mantener el mismo valor de CLSID en las distintas versiones, la aplicación puede usar los tipos COM a los que se hace referencia siempre que .NET Framework 4 o posterior esté instalado en el equipo de destino y la aplicación emplee métodos, propiedades o eventos que estén incluidos en los tipos COM a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="90e5e-124">Because applications like Office usually keep the same CLSID value across different versions, your application can use the referenced COM types as long as .NET Framework 4 or later is installed on the target computer and your application uses methods, properties, or events that are included in the referenced COM types.</span></span>  
  
 <span data-ttu-id="90e5e-125">La opción `-link` incrusta únicamente interfaces, estructuras y delegados.</span><span class="sxs-lookup"><span data-stu-id="90e5e-125">The `-link` option embeds only interfaces, structures, and delegates.</span></span> <span data-ttu-id="90e5e-126">No se admite la incrustación de clases COM.</span><span class="sxs-lookup"><span data-stu-id="90e5e-126">Embedding COM classes is not supported.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90e5e-127">Cuando se crea una instancia de un tipo COM incrustado en el código, hay que crear la instancia mediante la interfaz adecuada.</span><span class="sxs-lookup"><span data-stu-id="90e5e-127">When you create an instance of an embedded COM type in your code, you must create the instance by using the appropriate interface.</span></span> <span data-ttu-id="90e5e-128">Si se intenta crear una instancia de un tipo COM incrustado mediante la coclase, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="90e5e-128">Attempting to create an instance of an embedded COM type by using the CoClass causes an error.</span></span>  
  
 <span data-ttu-id="90e5e-129">Para establecer la opción `-link` en Visual Studio, agregue una referencia de ensamblado y establezca la propiedad `Embed Interop Types` en **true**.</span><span class="sxs-lookup"><span data-stu-id="90e5e-129">To set the `-link` option in Visual Studio, add an assembly reference and set the `Embed Interop Types` property to **true**.</span></span> <span data-ttu-id="90e5e-130">El valor predeterminado de la propiedad `Embed Interop Types` es **false**.</span><span class="sxs-lookup"><span data-stu-id="90e5e-130">The default for the `Embed Interop Types` property is **false**.</span></span>  
  
 <span data-ttu-id="90e5e-131">Si vincula a un ensamblado COM (ensamblado A) que a su vez hace referencia a otro ensamblado COM (ensamblado B), también debe vincular al ensamblado B si se cumple alguna de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="90e5e-131">If you link to a COM assembly (Assembly A) which itself references another COM assembly (Assembly B), you also have to link to Assembly B if either of the following is true:</span></span>  
  
- <span data-ttu-id="90e5e-132">Un tipo del ensamblado A hereda de un tipo o implementa una interfaz del ensamblado B.</span><span class="sxs-lookup"><span data-stu-id="90e5e-132">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="90e5e-133">Se invoca a un campo, una propiedad, un evento o un método que tiene un tipo de parámetro o un tipo de valor devuelto del ensamblado B.</span><span class="sxs-lookup"><span data-stu-id="90e5e-133">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="90e5e-134">Use [-libpath](libpath.md) para especificar el directorio en el que se encuentran una o varias de las referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="90e5e-134">Use [-libpath](libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="90e5e-135">Como sucede con [-reference](reference.md), la opción del compilador `-link` usa el archivo de respuesta Vbc.rsp, que hace referencia a ensamblados de .NET Framework que se usan con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="90e5e-135">Like the [-reference](reference.md) compiler option, the `-link` compiler option uses the Vbc.rsp response file, which references frequently used .NET Framework assemblies.</span></span> <span data-ttu-id="90e5e-136">Use la opción del compilador [-noconfig](noconfig.md) si no quiere que el compilador utilice el archivo Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="90e5e-136">Use the [-noconfig](noconfig.md) compiler option if you do not want the compiler to use the Vbc.rsp file.</span></span>  
  
 <span data-ttu-id="90e5e-137">La forma abreviada de `-link` es `-l`.</span><span class="sxs-lookup"><span data-stu-id="90e5e-137">The short form of `-link` is `-l`.</span></span>  
  
## <a name="generics-and-embedded-types"></a><span data-ttu-id="90e5e-138">Tipos incrustados y genéricos</span><span class="sxs-lookup"><span data-stu-id="90e5e-138">Generics and Embedded Types</span></span>  

 <span data-ttu-id="90e5e-139">En las secciones siguientes se describen las limitaciones sobre el uso de tipos genéricos en aplicaciones que incrustan tipos de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="90e5e-139">The following sections describe the limitations on using generic types in applications that embed interop types.</span></span>  
  
### <a name="generic-interfaces"></a><span data-ttu-id="90e5e-140">Interfaces genéricas</span><span class="sxs-lookup"><span data-stu-id="90e5e-140">Generic Interfaces</span></span>  

 <span data-ttu-id="90e5e-141">No se puede usar interfaces genéricas que se incrusten desde un ensamblado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="90e5e-141">Generic interfaces that are embedded from an interop assembly cannot be used.</span></span> <span data-ttu-id="90e5e-142">Esta implementación se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="90e5e-142">This is shown in the following example.</span></span>  
  
 [!code-vb[VbLinkCompiler#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/module1.vb#1)]  
  
### <a name="types-that-have-generic-parameters"></a><span data-ttu-id="90e5e-143">Tipos que tienen parámetros genéricos</span><span class="sxs-lookup"><span data-stu-id="90e5e-143">Types That Have Generic Parameters</span></span>  

 <span data-ttu-id="90e5e-144">Los tipos que tienen un parámetro genérico cuyo tipo se ha incrustado desde un ensamblado de interoperabilidad no se pueden usar si ese tipo pertenece a un ensamblado externo.</span><span class="sxs-lookup"><span data-stu-id="90e5e-144">Types that have a generic parameter whose type is embedded from an interop assembly cannot be used if that type is from an external assembly.</span></span> <span data-ttu-id="90e5e-145">Esta restricción no se aplica a las interfaces.</span><span class="sxs-lookup"><span data-stu-id="90e5e-145">This restriction does not apply to interfaces.</span></span> <span data-ttu-id="90e5e-146">Por ejemplo, considere la interfaz <xref:Microsoft.Office.Interop.Excel.Range> que se define en el ensamblado <xref:Microsoft.Office.Interop.Excel>.</span><span class="sxs-lookup"><span data-stu-id="90e5e-146">For example, consider the <xref:Microsoft.Office.Interop.Excel.Range> interface that is defined in the <xref:Microsoft.Office.Interop.Excel> assembly.</span></span> <span data-ttu-id="90e5e-147">Si una biblioteca inserta tipos de interoperabilidad desde el ensamblado <xref:Microsoft.Office.Interop.Excel> y expone un método que devuelve un tipo genérico que tiene un parámetro cuyo tipo es la interfaz <xref:Microsoft.Office.Interop.Excel.Range>, ese método debe devolver una interfaz genérica, como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="90e5e-147">If a library embeds interop types from the <xref:Microsoft.Office.Interop.Excel> assembly and exposes a method that returns a generic type that has a parameter whose type is the <xref:Microsoft.Office.Interop.Excel.Range> interface, that method must return a generic interface, as shown in the following code example.</span></span>  
  
 [!code-vb[VbLinkCompiler#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/utility.vb#2)]  
[!code-vb[VbLinkCompiler#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/utility.vb#3)]  
[!code-vb[VbLinkCompiler#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/utility.vb#4)]  
  
 <span data-ttu-id="90e5e-148">En el ejemplo siguiente, el código de cliente puede llamar al método que devuelve la interfaz genérica <xref:System.Collections.IList> sin errores.</span><span class="sxs-lookup"><span data-stu-id="90e5e-148">In the following example, client code can call the method that returns the <xref:System.Collections.IList> generic interface without error.</span></span>  
  
 [!code-vb[VbLinkCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vblinkcompiler/vb/module1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="90e5e-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="90e5e-149">Example</span></span>  

 <span data-ttu-id="90e5e-150">En la línea de comandos siguiente se compila el archivo de código fuente `OfficeApp.vb` y se hace referencia a ensamblados de `COMData1.dll` y `COMData2.dll` para generar `OfficeApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="90e5e-150">The following command line compiles source file `OfficeApp.vb` and reference assemblies from `COMData1.dll` and `COMData2.dll` to produce `OfficeApp.exe`.</span></span>  
  
```console  
vbc -link:COMData1.dll,COMData2.dll -out:OfficeApp.exe OfficeApp.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="90e5e-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="90e5e-151">See also</span></span>

- [<span data-ttu-id="90e5e-152">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="90e5e-152">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="90e5e-153">Tutorial: Inserción de tipos de ensamblados administrados</span><span class="sxs-lookup"><span data-stu-id="90e5e-153">Walkthrough: Embedding Types from Managed Assemblies</span></span>](../../../standard/assembly/embed-types-visual-studio.md)
- [<span data-ttu-id="90e5e-154">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90e5e-154">-reference (Visual Basic)</span></span>](reference.md)
- [<span data-ttu-id="90e5e-155">-noconfig</span><span class="sxs-lookup"><span data-stu-id="90e5e-155">-noconfig</span></span>](noconfig.md)
- [<span data-ttu-id="90e5e-156">-libpath</span><span class="sxs-lookup"><span data-stu-id="90e5e-156">-libpath</span></span>](libpath.md)
- [<span data-ttu-id="90e5e-157">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="90e5e-157">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="90e5e-158">Introducción a la interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="90e5e-158">Introduction to COM Interop</span></span>](../../programming-guide/com-interop/introduction-to-com-interop.md)
