---
title: Procedimiento para la creación manual de contenedores
description: Cree contenedores de los tipos COM manualmente. Use un archivo IDL existente o una biblioteca de tipos, o cree declaraciones administradas y exporte el ensamblado a una biblioteca de tipos.
ms.date: 03/30/2017
helpviewer_keywords:
- wrappers, creating manually
ms.assetid: cc2a70d8-6a58-4071-a8cf-ce28c018c09b
ms.openlocfilehash: 0321e98e6237e54397db7e583546fd69803ab7e1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275962"
---
# <a name="how-to-create-wrappers-manually"></a><span data-ttu-id="11e80-104">Procedimiento para la creación manual de contenedores</span><span class="sxs-lookup"><span data-stu-id="11e80-104">How to: Create Wrappers Manually</span></span>

<span data-ttu-id="11e80-105">Si decide declarar manualmente los tipos COM en código fuente administrado, lo mejor es empezar con un archivo o una biblioteca de tipos existente del Lenguaje de definición de interfaz (IDL).</span><span class="sxs-lookup"><span data-stu-id="11e80-105">If you decide to declare COM types manually in managed source code, the best place to start is with an existing Interface Definition Language (IDL) file or type library.</span></span> <span data-ttu-id="11e80-106">Cuando no tiene el archivo IDL o no puede generar un archivo de biblioteca de tipos, puede simular los tipos COM si crea declaraciones administradas y exporta el ensamblado resultante a una biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="11e80-106">When you do not have the IDL file or cannot generate a type library file, you can simulate the COM types by creating managed declarations and exporting the resulting assembly to a type library.</span></span>  
  
### <a name="to-simulate-com-types-from-managed-source"></a><span data-ttu-id="11e80-107">Para simular tipos COM a partir de código fuente administrado</span><span class="sxs-lookup"><span data-stu-id="11e80-107">To simulate COM types from managed source</span></span>  
  
1. <span data-ttu-id="11e80-108">Declare los tipos en un lenguaje conforme a CLS (Common Language Specification) y compile el archivo.</span><span class="sxs-lookup"><span data-stu-id="11e80-108">Declare the types in a language that is compliant with the Common Language Specification (CLS) and compile the file.</span></span>  
  
2. <span data-ttu-id="11e80-109">Exporte el ensamblado que contiene los tipos con el [Exportador de la biblioteca de tipos (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="11e80-109">Export the assembly containing the types with the [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span></span>  
  
3. <span data-ttu-id="11e80-110">Utilice la biblioteca de tipos COM exportada como base para declarar tipos administrados orientados a COM.</span><span class="sxs-lookup"><span data-stu-id="11e80-110">Use the exported COM type library as a basis for declaring COM-oriented managed types.</span></span>  
  
### <a name="to-create-a-runtime-callable-wrapper-rcw"></a><span data-ttu-id="11e80-111">Para crear un contenedor invocable en tiempo de ejecución (RCW)</span><span class="sxs-lookup"><span data-stu-id="11e80-111">To create a runtime callable wrapper (RCW)</span></span>  
  
1. <span data-ttu-id="11e80-112">Suponiendo que tiene un archivo IDL o un archivo de biblioteca de tipos, decida qué clases e interfaces desea incluir en el RCW personalizado.</span><span class="sxs-lookup"><span data-stu-id="11e80-112">Assuming that you have an IDL file or type library file, decide which classes and interfaces you want to include in the custom RCW.</span></span> <span data-ttu-id="11e80-113">Puede excluir cualquier tipo que no piense utilizar directa o indirectamente en su aplicación.</span><span class="sxs-lookup"><span data-stu-id="11e80-113">You can exclude any types that you do not intend to use directly or indirectly in your application.</span></span>  
  
2. <span data-ttu-id="11e80-114">Cree un archivo código fuente en un lenguaje conforme a CLS y declare los tipos.</span><span class="sxs-lookup"><span data-stu-id="11e80-114">Create a source file in a CLS-compliant language and declare the types.</span></span> <span data-ttu-id="11e80-115">Vea [Resumen de la conversión de bibliotecas de tipos en ensamblados](/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100)) para obtener una descripción completa del proceso de conversión de importación.</span><span class="sxs-lookup"><span data-stu-id="11e80-115">See [Type Library to Assembly Conversion Summary](/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100)) for a complete description of the import conversion process.</span></span> <span data-ttu-id="11e80-116">Cuando se crea un RCW personalizado, se realiza manualmente la conversión de tipos proporcionada por el [Importador de la biblioteca de tipos (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span><span class="sxs-lookup"><span data-stu-id="11e80-116">Effectively, when you create a custom RCW, you are manually performing the type conversion activity provided by the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="11e80-117">El ejemplo de la siguiente sección muestra los tipos de un IDL o un archivo de biblioteca de tipos y sus tipos correspondientes en código de C#.</span><span class="sxs-lookup"><span data-stu-id="11e80-117">The example in the next section shows types in an IDL or type library file and their corresponding types in C# code.</span></span>  
  
3. <span data-ttu-id="11e80-118">Una vez completadas las declaraciones, compile el archivo de la misma forma que compila cualquier otro código fuente administrado.</span><span class="sxs-lookup"><span data-stu-id="11e80-118">When the declarations are complete, compile the file as you compile any other managed source code.</span></span>  
  
4. <span data-ttu-id="11e80-119">Como ocurre con los tipos importados con Tlbimp.exe, algunos requieren información adicional, que puede agregar directamente al código.</span><span class="sxs-lookup"><span data-stu-id="11e80-119">As with the types imported with Tlbimp.exe, some require additional information, which you can add directly to your code.</span></span> <span data-ttu-id="11e80-120">Para obtener más detalles, vea [Cómo: Editar ensamblados de interoperabilidad](/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="11e80-120">For details, see [How to: Edit Interop Assemblies](/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="11e80-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="11e80-121">Example</span></span>  

 <span data-ttu-id="11e80-122">En el siguiente código se muestra un ejemplo de la interfaz `ISATest` y la clase `SATest` en IDL, y los tipos correspondientes en código fuente de C#.</span><span class="sxs-lookup"><span data-stu-id="11e80-122">The following code shows an example of the `ISATest` interface and `SATest` class in IDL and the corresponding types in C# source code.</span></span>  
  
 <span data-ttu-id="11e80-123">**Archivo IDL o de biblioteca de tipos**</span><span class="sxs-lookup"><span data-stu-id="11e80-123">**IDL or type library file**</span></span>  
  
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
  
 <span data-ttu-id="11e80-124">**Contenedor en código fuente administrado**</span><span class="sxs-lookup"><span data-stu-id="11e80-124">**Wrapper in managed source code**</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="11e80-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="11e80-125">See also</span></span>

- <span data-ttu-id="11e80-126">[Personalización de contenedores RCW](/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="11e80-126">[Customizing Runtime Callable Wrappers](/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span></span>
- <span data-ttu-id="11e80-127">[Tipos de datos COM](/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="11e80-127">[COM Data Types](/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span></span>
- <span data-ttu-id="11e80-128">[Cómo: Editar ensamblados de interoperabilidad](/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="11e80-128">[How to: Edit Interop Assemblies](/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100))</span></span>
- <span data-ttu-id="11e80-129">[Resumen de la conversión de bibliotecas de tipos en ensamblados](/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="11e80-129">[Type Library to Assembly Conversion Summary](/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span></span>
- [<span data-ttu-id="11e80-130">TlbImp.exe (Importador de la biblioteca de tipos)</span><span class="sxs-lookup"><span data-stu-id="11e80-130">Tlbimp.exe (Type Library Importer)</span></span>](../tools/tlbimp-exe-type-library-importer.md)
- [<span data-ttu-id="11e80-131">Tlbexp.exe (Exportador de la biblioteca de tipos)</span><span class="sxs-lookup"><span data-stu-id="11e80-131">Tlbexp.exe (Type Library Exporter)</span></span>](../tools/tlbexp-exe-type-library-exporter.md)
