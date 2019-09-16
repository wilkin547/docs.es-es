---
title: Procedimiento para la creación manual de contenedores
ms.date: 03/30/2017
helpviewer_keywords:
- wrappers, creating manually
ms.assetid: cc2a70d8-6a58-4071-a8cf-ce28c018c09b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5db0ec9050c74b27d3ee25a99dcf8e2319835ffb
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894218"
---
# <a name="how-to-create-wrappers-manually"></a><span data-ttu-id="5bbb1-102">Procedimiento para la creación manual de contenedores</span><span class="sxs-lookup"><span data-stu-id="5bbb1-102">How to: Create Wrappers Manually</span></span>
<span data-ttu-id="5bbb1-103">Si decide declarar manualmente los tipos COM en código fuente administrado, lo mejor es empezar con un archivo o una biblioteca de tipos existente del Lenguaje de definición de interfaz (IDL).</span><span class="sxs-lookup"><span data-stu-id="5bbb1-103">If you decide to declare COM types manually in managed source code, the best place to start is with an existing Interface Definition Language (IDL) file or type library.</span></span> <span data-ttu-id="5bbb1-104">Cuando no tiene el archivo IDL o no puede generar un archivo de biblioteca de tipos, puede simular los tipos COM si crea declaraciones administradas y exporta el ensamblado resultante a una biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="5bbb1-104">When you do not have the IDL file or cannot generate a type library file, you can simulate the COM types by creating managed declarations and exporting the resulting assembly to a type library.</span></span>  
  
### <a name="to-simulate-com-types-from-managed-source"></a><span data-ttu-id="5bbb1-105">Para simular tipos COM a partir de código fuente administrado</span><span class="sxs-lookup"><span data-stu-id="5bbb1-105">To simulate COM types from managed source</span></span>  
  
1. <span data-ttu-id="5bbb1-106">Declare los tipos en un lenguaje conforme a CLS (Common Language Specification) y compile el archivo.</span><span class="sxs-lookup"><span data-stu-id="5bbb1-106">Declare the types in a language that is compliant with the Common Language Specification (CLS) and compile the file.</span></span>  
  
2. <span data-ttu-id="5bbb1-107">Exporte el ensamblado que contiene los tipos con el [Exportador de la biblioteca de tipos (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="5bbb1-107">Export the assembly containing the types with the [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span></span>  
  
3. <span data-ttu-id="5bbb1-108">Utilice la biblioteca de tipos COM exportada como base para declarar tipos administrados orientados a COM.</span><span class="sxs-lookup"><span data-stu-id="5bbb1-108">Use the exported COM type library as a basis for declaring COM-oriented managed types.</span></span>  
  
### <a name="to-create-a-runtime-callable-wrapper-rcw"></a><span data-ttu-id="5bbb1-109">Para crear un contenedor invocable en tiempo de ejecución (RCW)</span><span class="sxs-lookup"><span data-stu-id="5bbb1-109">To create a runtime callable wrapper (RCW)</span></span>  
  
1. <span data-ttu-id="5bbb1-110">Suponiendo que tiene un archivo IDL o un archivo de biblioteca de tipos, decida qué clases e interfaces desea incluir en el RCW personalizado.</span><span class="sxs-lookup"><span data-stu-id="5bbb1-110">Assuming that you have an IDL file or type library file, decide which classes and interfaces you want to include in the custom RCW.</span></span> <span data-ttu-id="5bbb1-111">Puede excluir cualquier tipo que no piense utilizar directa o indirectamente en su aplicación.</span><span class="sxs-lookup"><span data-stu-id="5bbb1-111">You can exclude any types that you do not intend to use directly or indirectly in your application.</span></span>  
  
2. <span data-ttu-id="5bbb1-112">Cree un archivo código fuente en un lenguaje conforme a CLS y declare los tipos.</span><span class="sxs-lookup"><span data-stu-id="5bbb1-112">Create a source file in a CLS-compliant language and declare the types.</span></span> <span data-ttu-id="5bbb1-113">Vea [Resumen de la conversión de bibliotecas de tipos en ensamblados](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100)) para obtener una descripción completa del proceso de conversión de importación.</span><span class="sxs-lookup"><span data-stu-id="5bbb1-113">See [Type Library to Assembly Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100)) for a complete description of the import conversion process.</span></span> <span data-ttu-id="5bbb1-114">Cuando se crea un RCW personalizado, se realiza manualmente la conversión de tipos proporcionada por el [Importador de la biblioteca de tipos (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span><span class="sxs-lookup"><span data-stu-id="5bbb1-114">Effectively, when you create a custom RCW, you are manually performing the type conversion activity provided by the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="5bbb1-115">El ejemplo de la siguiente sección muestra los tipos de un IDL o un archivo de biblioteca de tipos y sus tipos correspondientes en código de C#.</span><span class="sxs-lookup"><span data-stu-id="5bbb1-115">The example in the next section shows types in an IDL or type library file and their corresponding types in C# code.</span></span>  
  
3. <span data-ttu-id="5bbb1-116">Una vez completadas las declaraciones, compile el archivo de la misma forma que compila cualquier otro código fuente administrado.</span><span class="sxs-lookup"><span data-stu-id="5bbb1-116">When the declarations are complete, compile the file as you compile any other managed source code.</span></span>  
  
4. <span data-ttu-id="5bbb1-117">Como ocurre con los tipos importados con Tlbimp.exe, algunos requieren información adicional, que puede agregar directamente al código.</span><span class="sxs-lookup"><span data-stu-id="5bbb1-117">As with the types imported with Tlbimp.exe, some require additional information, which you can add directly to your code.</span></span> <span data-ttu-id="5bbb1-118">Para obtener más detalles, vea [Cómo: Editar ensamblados de interoperabilidad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="5bbb1-118">For details, see [How to: Edit Interop Assemblies](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bbb1-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bbb1-119">Example</span></span>  
 <span data-ttu-id="5bbb1-120">En el siguiente código se muestra un ejemplo de la interfaz `ISATest` y la clase `SATest` en IDL, y los tipos correspondientes en código fuente de C#.</span><span class="sxs-lookup"><span data-stu-id="5bbb1-120">The following code shows an example of the `ISATest` interface and `SATest` class in IDL and the corresponding types in C# source code.</span></span>  
  
 <span data-ttu-id="5bbb1-121">**Archivo IDL o de biblioteca de tipos**</span><span class="sxs-lookup"><span data-stu-id="5bbb1-121">**IDL or type library file**</span></span>  
  
```cpp
 [  
object,  
uuid(40A8C65D-2448-447A-B786-64682CBEF133),  
dual,  
helpstring("ISATest Interface"),  
pointer_default(unique)  
 ]  
interface ISATest : IDispatch  
 {  
[id(1), helpstring("method InSArray")]   
HRESULT InSArray([in] SAFEARRAY(int) *ppsa, [out,retval] int *pSum);  
 };  
 [  
uuid(116CCA1E-7E39-4515-9849-90790DA6431E),  
helpstring("SATest Class")  
 ]  
coclass SATest  
 {  
  [default] interface ISATest;  
 };  
```  
  
 <span data-ttu-id="5bbb1-122">**Contenedor en código fuente administrado**</span><span class="sxs-lookup"><span data-stu-id="5bbb1-122">**Wrapper in managed source code**</span></span>  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
using System.Runtime.CompilerServices;  
  
[assembly:Guid("E4A992B8-6F5C-442C-96E7-C4778924C753")]  
[assembly:ImportedFromTypeLib("SAServerLib")]  
namespace SAServer  
{  
 [ComImport]  
 [Guid("40A8C65D-2448-447A-B786-64682CBEF133")]  
 [TypeLibType(TypeLibTypeFlags.FLicensed)]  
 public interface ISATest  
 {  
  [DispId(1)]  
  //[MethodImpl(MethodImplOptions.InternalCall,  
  // MethodCodeType=MethodCodeType.Runtime)]  
  int InSArray( [MarshalAs(UnmanagedType.SafeArray,  
      SafeArraySubType=VarEnum.VT_I4)] ref int[] param );  
 }   
 [ComImport]  
 [Guid("116CCA1E-7E39-4515-9849-90790DA6431E")]  
 [ClassInterface(ClassInterfaceType.None)]  
 [TypeLibType(TypeLibTypeFlags.FCanCreate)]  
 public class SATest : ISATest  
 {  
  [DispId(1)]  
  [MethodImpl(MethodImplOptions.InternalCall,   
  MethodCodeType=MethodCodeType.Runtime)]  
  extern int ISATest.InSArray( [MarshalAs(UnmanagedType.SafeArray,   
  SafeArraySubType=VarEnum.VT_I4)] ref int[] param );  
 }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5bbb1-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bbb1-123">See also</span></span>

- <span data-ttu-id="5bbb1-124">[Personalización de contenedores RCW](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5bbb1-124">[Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span></span>
- <span data-ttu-id="5bbb1-125">[Tipos de datos COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5bbb1-125">[COM Data Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span></span>
- <span data-ttu-id="5bbb1-126">[Cómo: Editar ensamblados de interoperabilidad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5bbb1-126">[How to: Edit Interop Assemblies](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100))</span></span>
- <span data-ttu-id="5bbb1-127">[Resumen de la conversión de bibliotecas de tipos en ensamblados](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5bbb1-127">[Type Library to Assembly Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span></span>
- [<span data-ttu-id="5bbb1-128">TlbImp.exe (Importador de la biblioteca de tipos)</span><span class="sxs-lookup"><span data-stu-id="5bbb1-128">Tlbimp.exe (Type Library Importer)</span></span>](../tools/tlbimp-exe-type-library-importer.md)
- [<span data-ttu-id="5bbb1-129">Tlbexp.exe (Exportador de la biblioteca de tipos)</span><span class="sxs-lookup"><span data-stu-id="5bbb1-129">Tlbexp.exe (Type Library Exporter)</span></span>](../tools/tlbexp-exe-type-library-exporter.md)
