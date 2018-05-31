---
title: 'Cómo: Hacer referencia a tipos de .NET desde COM'
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- importing type library
- COM interop, referencing .NET types
- interoperation with unmanaged code, referencing .NET types
- referencing .NET types
- interoperation with unmanaged code, importing type library
- type libraries
- COM interop, importing type library
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0333cd73240e685b46917d85afe0876532db3fd1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33391905"
---
# <a name="how-to-reference-net-types-from-com"></a><span data-ttu-id="02452-102">Cómo: Hacer referencia a tipos de .NET desde COM</span><span class="sxs-lookup"><span data-stu-id="02452-102">How to: Reference .NET Types from COM</span></span>
<span data-ttu-id="02452-103">Desde el punto de vista del código de cliente y servidor, las diferencias entre COM y .NET Framework son prácticamente inapreciables.</span><span class="sxs-lookup"><span data-stu-id="02452-103">From the point of view of client and server code, the differences between COM and the .NET Framework are largely invisible.</span></span> <span data-ttu-id="02452-104">Los clientes Microsoft Visual Basic pueden ver los objetos de .NET en el Examinador de objetos, que expone los métodos y la sintaxis, las propiedades, y los campos de los objetos exactamente del mismo modo que si se tratase de cualquier otro objeto COM.</span><span class="sxs-lookup"><span data-stu-id="02452-104">Microsoft Visual Basic clients can view a .NET object in the object browser, which exposes the object methods and syntax, properties, and fields exactly as if it were any other COM object.</span></span>  
  
 <span data-ttu-id="02452-105">El proceso de importación de una biblioteca de tipos es algo más complicado para los clientes C++, a pesar de que se utilizan las mismas herramientas para exportar los metadatos a una biblioteca de tipos COM.</span><span class="sxs-lookup"><span data-stu-id="02452-105">The process for importing a type library is slightly more complicated for C++ clients, although you use the same tools to export metadata to a COM type library.</span></span> <span data-ttu-id="02452-106">Para hacer referencia a miembros de objetos de .NET desde un cliente C++ no administrado, haga referencia al archivo TLB (generado con Tlbexp.exe) con la directiva **#import**.</span><span class="sxs-lookup"><span data-stu-id="02452-106">To reference .NET object members from an unmanaged C++ client, reference the TLB file (produced with Tlbexp.exe) with the **#import** directive.</span></span> <span data-ttu-id="02452-107">Cuando se hace referencia a una biblioteca de tipos desde C++, es necesario especificar la opción **raw_interfaces_only** o importar las definiciones de la biblioteca de clases base, Mscorlib.tlb.</span><span class="sxs-lookup"><span data-stu-id="02452-107">When referencing a type library from C++, you must either specify the **raw_interfaces_only** option or import the definitions in the base class library, Mscorlib.tlb.</span></span>  
  
### <a name="to-import-a-library"></a><span data-ttu-id="02452-108">Para importar una biblioteca</span><span class="sxs-lookup"><span data-stu-id="02452-108">To import a library</span></span>  
  
-   <span data-ttu-id="02452-109">Especifique la opción **raw_interfaces_only** en la directiva **#import**.</span><span class="sxs-lookup"><span data-stu-id="02452-109">Specify the **raw_interfaces_only** option in the **#import** directive.</span></span> <span data-ttu-id="02452-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="02452-110">For example:</span></span>  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     <span data-ttu-id="02452-111">O bien</span><span class="sxs-lookup"><span data-stu-id="02452-111">-or-</span></span>  
  
-   <span data-ttu-id="02452-112">Incluya una directiva #import para Mscorlib.tlb.</span><span class="sxs-lookup"><span data-stu-id="02452-112">Include an #import directive for Mscorlib.tlb.</span></span> <span data-ttu-id="02452-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="02452-113">For example:</span></span>  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="02452-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="02452-114">See Also</span></span>  
 [<span data-ttu-id="02452-115">Exponer componentes de .NET Framework en COM</span><span class="sxs-lookup"><span data-stu-id="02452-115">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)  
 [<span data-ttu-id="02452-116">Registrar ensamblados con COM</span><span class="sxs-lookup"><span data-stu-id="02452-116">Registering Assemblies with COM</span></span>](registering-assemblies-with-com.md)  
 <span data-ttu-id="02452-117">[Llamada a un objeto de .NET](https://msdn.microsoft.com/library/40c9626c-aea6-4bad-b8f0-c1de462efd33(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="02452-117">[Calling a .NET Object](https://msdn.microsoft.com/library/40c9626c-aea6-4bad-b8f0-c1de462efd33(v=vs.100))</span></span>  
 <span data-ttu-id="02452-118">[Implementar una aplicación para obtener acceso a COM](https://msdn.microsoft.com/library/fb63564c-c1b9-4655-a094-a235625882ce(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="02452-118">[Deploying an Application for COM Access](https://msdn.microsoft.com/library/fb63564c-c1b9-4655-a094-a235625882ce(v=vs.100))</span></span>
