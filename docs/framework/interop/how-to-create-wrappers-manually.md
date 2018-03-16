---
title: "Cómo: Crear contenedores manualmente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wrappers, creating manually
ms.assetid: cc2a70d8-6a58-4071-a8cf-ce28c018c09b
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7ac7afdd85037d50bdda9fae0a33896dc441bce5
ms.sourcegitcommit: 1c0b0f082b3f300e54b4d069b317ac724c88ddc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2018
---
# <a name="how-to-create-wrappers-manually"></a><span data-ttu-id="9c19c-102">Cómo: Crear contenedores manualmente</span><span class="sxs-lookup"><span data-stu-id="9c19c-102">How to: Create Wrappers Manually</span></span>
<span data-ttu-id="9c19c-103">Si decide declarar manualmente los tipos COM en código fuente administrado, lo mejor es empezar con un archivo o una biblioteca de tipos existente del Lenguaje de definición de interfaz (IDL).</span><span class="sxs-lookup"><span data-stu-id="9c19c-103">If you decide to declare COM types manually in managed source code, the best place to start is with an existing Interface Definition Language (IDL) file or type library.</span></span> <span data-ttu-id="9c19c-104">Cuando no tiene el archivo IDL o no puede generar un archivo de biblioteca de tipos, puede simular los tipos COM si crea declaraciones administradas y exporta el ensamblado resultante a una biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="9c19c-104">When you do not have the IDL file or cannot generate a type library file, you can simulate the COM types by creating managed declarations and exporting the resulting assembly to a type library.</span></span>  
  
### <a name="to-simulate-com-types-from-managed-source"></a><span data-ttu-id="9c19c-105">Para simular tipos COM a partir de código fuente administrado</span><span class="sxs-lookup"><span data-stu-id="9c19c-105">To simulate COM types from managed source</span></span>  
  
1.  <span data-ttu-id="9c19c-106">Declare los tipos en un lenguaje conforme a CLS (Common Language Specification) y compile el archivo.</span><span class="sxs-lookup"><span data-stu-id="9c19c-106">Declare the types in a language that is compliant with the Common Language Specification (CLS) and compile the file.</span></span>  
  
2.  <span data-ttu-id="9c19c-107">Exporte el ensamblado que contiene los tipos con el [Exportador de la biblioteca de tipos (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="9c19c-107">Export the assembly containing the types with the [Type Library Exporter (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span></span>  
  
3.  <span data-ttu-id="9c19c-108">Utilice la biblioteca de tipos COM exportada como base para declarar tipos administrados orientados a COM.</span><span class="sxs-lookup"><span data-stu-id="9c19c-108">Use the exported COM type library as a basis for declaring COM-oriented managed types.</span></span>  
  
### <a name="to-create-a-runtime-callable-wrapper-rcw"></a><span data-ttu-id="9c19c-109">Para crear un contenedor invocable en tiempo de ejecución (RCW)</span><span class="sxs-lookup"><span data-stu-id="9c19c-109">To create a runtime callable wrapper (RCW)</span></span>  
  
1.  <span data-ttu-id="9c19c-110">Suponiendo que tiene un archivo IDL o un archivo de biblioteca de tipos, decida qué clases e interfaces desea incluir en el RCW personalizado.</span><span class="sxs-lookup"><span data-stu-id="9c19c-110">Assuming that you have an IDL file or type library file, decide which classes and interfaces you want to include in the custom RCW.</span></span> <span data-ttu-id="9c19c-111">Puede excluir cualquier tipo que no piense utilizar directa o indirectamente en su aplicación.</span><span class="sxs-lookup"><span data-stu-id="9c19c-111">You can exclude any types that you do not intend to use directly or indirectly in your application.</span></span>  
  
2.  <span data-ttu-id="9c19c-112">Cree un archivo código fuente en un lenguaje conforme a CLS y declare los tipos.</span><span class="sxs-lookup"><span data-stu-id="9c19c-112">Create a source file in a CLS-compliant language and declare the types.</span></span> <span data-ttu-id="9c19c-113">Vea [Resumen de la conversión de bibliotecas de tipos en ensamblados](http://msdn.microsoft.com/library/bf3f90c5-4770-4ab8-895c-3ba1055cc958) para obtener una descripción completa del proceso de conversión de importación.</span><span class="sxs-lookup"><span data-stu-id="9c19c-113">See [Type Library to Assembly Conversion Summary](http://msdn.microsoft.com/library/bf3f90c5-4770-4ab8-895c-3ba1055cc958) for a complete description of the import conversion process.</span></span> <span data-ttu-id="9c19c-114">Cuando se crea un RCW personalizado, se realiza manualmente la conversión de tipos proporcionada por el [Importador de la biblioteca de tipos (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md).</span><span class="sxs-lookup"><span data-stu-id="9c19c-114">Effectively, when you create a custom RCW, you are manually performing the type conversion activity provided by the [Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="9c19c-115">El ejemplo de la siguiente sección muestra los tipos de un IDL o un archivo de biblioteca de tipos y sus tipos correspondientes en código de C#.</span><span class="sxs-lookup"><span data-stu-id="9c19c-115">The example in the next section shows types in an IDL or type library file and their corresponding types in C# code.</span></span>  
  
3.  <span data-ttu-id="9c19c-116">Una vez completadas las declaraciones, compile el archivo de la misma forma que compila cualquier otro código fuente administrado.</span><span class="sxs-lookup"><span data-stu-id="9c19c-116">When the declarations are complete, compile the file as you compile any other managed source code.</span></span>  
  
4.  <span data-ttu-id="9c19c-117">Como ocurre con los tipos importados con Tlbimp.exe, algunos requieren información adicional, que puede agregar directamente al código.</span><span class="sxs-lookup"><span data-stu-id="9c19c-117">As with the types imported with Tlbimp.exe, some require additional information, which you can add directly to your code.</span></span> <span data-ttu-id="9c19c-118">Para obtener más detalles, vea [Cómo: Editar ensamblados de interoperabilidad](https://msdn.microsoft.com/library/16aacb20-2269-42bf-a812-b6a7df17e277(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="9c19c-118">For details, see [How to: Edit Interop Assemblies](https://msdn.microsoft.com/library/16aacb20-2269-42bf-a812-b6a7df17e277(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c19c-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9c19c-119">Example</span></span>  
 <span data-ttu-id="9c19c-120">En el siguiente código se muestra un ejemplo de la interfaz `ISATest` y la clase `SATest` en IDL, y los tipos correspondientes en código fuente de C#.</span><span class="sxs-lookup"><span data-stu-id="9c19c-120">The following code shows an example of the `ISATest` interface and `SATest` class in IDL and the corresponding types in C# source code.</span></span>  
  
 <span data-ttu-id="9c19c-121">**Archivo IDL o de biblioteca de tipos**</span><span class="sxs-lookup"><span data-stu-id="9c19c-121">**IDL or type library file**</span></span>  
  
```  
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
  
 <span data-ttu-id="9c19c-122">**Contenedor en código fuente administrado**</span><span class="sxs-lookup"><span data-stu-id="9c19c-122">**Wrapper in managed source code**</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9c19c-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c19c-123">See Also</span></span>  
 [<span data-ttu-id="9c19c-124">Personalización de contenedores RCW</span><span class="sxs-lookup"><span data-stu-id="9c19c-124">Customizing Runtime Callable Wrappers</span></span>](http://msdn.microsoft.com/library/4652beaf-77d0-4f37-9687-ca193288c0be)  
 [<span data-ttu-id="9c19c-125">Tipos de datos COM</span><span class="sxs-lookup"><span data-stu-id="9c19c-125">COM Data Types</span></span>](http://msdn.microsoft.com/library/f93ae35d-a416-4218-8700-c8218cc90061)  
 [<span data-ttu-id="9c19c-126">Cómo: Editar ensamblados de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="9c19c-126">How to: Edit Interop Assemblies</span></span>](http://msdn.microsoft.com/library/16aacb20-2269-42bf-a812-b6a7df17e277)  
 [<span data-ttu-id="9c19c-127">Resumen de la conversión de bibliotecas de tipos en ensamblados</span><span class="sxs-lookup"><span data-stu-id="9c19c-127">Type Library to Assembly Conversion Summary</span></span>](http://msdn.microsoft.com/library/bf3f90c5-4770-4ab8-895c-3ba1055cc958)  
 [<span data-ttu-id="9c19c-128">TlbImp.exe (Importador de la biblioteca de tipos)</span><span class="sxs-lookup"><span data-stu-id="9c19c-128">Tlbimp.exe (Type Library Importer)</span></span>](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
 [<span data-ttu-id="9c19c-129">Tlbexp.exe (Exportador de la biblioteca de tipos)</span><span class="sxs-lookup"><span data-stu-id="9c19c-129">Tlbexp.exe (Type Library Exporter)</span></span>](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)
