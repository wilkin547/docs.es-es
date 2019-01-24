---
title: Procedimiento Objetos de referencia COM desde Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
ms.openlocfilehash: c9d6a2ad6146ebd90be330813a44d092c044348b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534935"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a><span data-ttu-id="7f4dc-102">Procedimiento Objetos de referencia COM desde Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7f4dc-102">How to: Reference COM Objects from Visual Basic</span></span>
<span data-ttu-id="7f4dc-103">En Visual Basic, agregar referencias a objetos COM que tienen bibliotecas de tipos requiere la creación de un ensamblado de interoperabilidad de la biblioteca COM.</span><span class="sxs-lookup"><span data-stu-id="7f4dc-103">In Visual Basic, adding references to COM objects that have type libraries requires the creation of an interop assembly for the COM library.</span></span> <span data-ttu-id="7f4dc-104">Las referencias a los miembros del objeto COM se enrutan al ensamblado de interoperabilidad y, a continuación, se reenvían al objeto COM real.</span><span class="sxs-lookup"><span data-stu-id="7f4dc-104">References to the members of the COM object are routed to the interop assembly and then forwarded to the actual COM object.</span></span> <span data-ttu-id="7f4dc-105">Las respuestas desde el objeto COM se enrutan al ensamblado de interoperabilidad y se reenvían a su [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] aplicación.</span><span class="sxs-lookup"><span data-stu-id="7f4dc-105">Responses from the COM object are routed to the interop assembly and forwarded to your [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] application.</span></span>  
  
 <span data-ttu-id="7f4dc-106">Puede hacer referencia a un objeto COM sin usar un ensamblado de interoperabilidad insertando la información de tipo para el objeto COM en un ensamblado. NET.</span><span class="sxs-lookup"><span data-stu-id="7f4dc-106">You can reference a COM object without using an interop assembly by embedding the type information for the COM object in a .NET assembly.</span></span> <span data-ttu-id="7f4dc-107">Para incrustar información de tipo, establezca el `Embed Interop Types` propiedad `True` para la referencia al objeto COM.</span><span class="sxs-lookup"><span data-stu-id="7f4dc-107">To embed type information, set the `Embed Interop Types` property to `True` for the reference to the COM object.</span></span> <span data-ttu-id="7f4dc-108">Si está compilando mediante el compilador de línea de comandos, use el `/link` opción para hacer referencia a la biblioteca COM.</span><span class="sxs-lookup"><span data-stu-id="7f4dc-108">If you are compiling by using the command-line compiler, use the `/link` option to reference the COM library.</span></span> <span data-ttu-id="7f4dc-109">Para obtener más información, consulte [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span><span class="sxs-lookup"><span data-stu-id="7f4dc-109">For more information, see [/link (Visual Basic)](../../../visual-basic/reference/command-line-compiler/link.md).</span></span>  
  
 <span data-ttu-id="7f4dc-110">Visual Basic crea automáticamente ensamblados de interoperabilidad cuando se agrega una referencia a una biblioteca de tipos desde el entorno de desarrollo integrado (IDE).</span><span class="sxs-lookup"><span data-stu-id="7f4dc-110">Visual Basic automatically creates interop assemblies when you add a reference to a type library from the integrated development environment (IDE).</span></span> <span data-ttu-id="7f4dc-111">Cuando se trabaja desde la línea de comandos, puede usar la utilidad Tlbimp para crear manualmente los ensamblados de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="7f4dc-111">When working from the command line, you can use the Tlbimp utility to manually create interop assemblies.</span></span>  
  
### <a name="to-add-references-to-com-objects"></a><span data-ttu-id="7f4dc-112">Para agregar referencias a objetos COM</span><span class="sxs-lookup"><span data-stu-id="7f4dc-112">To add references to COM objects</span></span>  
  
1.  <span data-ttu-id="7f4dc-113">En el **proyecto** menú, elija **Agregar referencia** y, a continuación, haga clic en el **COM** ficha en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7f4dc-113">On the **Project** menu, choose **Add Reference** and then click the **COM** tab in the dialog box.</span></span>  
  
2.  <span data-ttu-id="7f4dc-114">Seleccione el componente que desea usar en la lista de objetos COM.</span><span class="sxs-lookup"><span data-stu-id="7f4dc-114">Select the component you want to use from the list of COM objects.</span></span>  
  
3.  <span data-ttu-id="7f4dc-115">Para simplificar el acceso al ensamblado de interoperabilidad, agregue un `Imports` instrucción a la parte superior de la clase o módulo en el que va a utilizar el objeto COM.</span><span class="sxs-lookup"><span data-stu-id="7f4dc-115">To simplify access to the interop assembly, add an `Imports` statement to the top of the class or module in which you will use the COM object.</span></span> <span data-ttu-id="7f4dc-116">Por ejemplo, en el ejemplo de código siguiente se importa el espacio de nombres `INKEDLib` para los objetos que se hace referenciados en el `Microsoft InkEdit Control 1.0` biblioteca.</span><span class="sxs-lookup"><span data-stu-id="7f4dc-116">For example, the following code example imports the namespace `INKEDLib` for objects referenced in the `Microsoft InkEdit Control 1.0` library.</span></span>  
  
     [!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a><span data-ttu-id="7f4dc-117">Para crear un ensamblado de interoperabilidad mediante Tlbimp</span><span class="sxs-lookup"><span data-stu-id="7f4dc-117">To create an interop assembly using Tlbimp</span></span>  
  
1.  <span data-ttu-id="7f4dc-118">Agregue la ubicación de Tlbimp a la ruta de búsqueda, si ya no es parte de la ruta de acceso de búsqueda y no está actualmente en el directorio donde se encuentra.</span><span class="sxs-lookup"><span data-stu-id="7f4dc-118">Add the location of Tlbimp to the search path, if it is not already part of the search path and you are not currently in the directory where it is located.</span></span>  
  
2.  <span data-ttu-id="7f4dc-119">Llame a Tlbimp desde un símbolo del sistema, que proporciona la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="7f4dc-119">Call Tlbimp from a command prompt, providing the following information:</span></span>  
  
    -   <span data-ttu-id="7f4dc-120">Nombre y la ubicación del archivo DLL que contiene la biblioteca de tipos</span><span class="sxs-lookup"><span data-stu-id="7f4dc-120">Name and location of the DLL that contains the type library</span></span>  
  
    -   <span data-ttu-id="7f4dc-121">Nombre y la ubicación del espacio de nombres donde se debe colocar la información</span><span class="sxs-lookup"><span data-stu-id="7f4dc-121">Name and location of the namespace where the information should be placed</span></span>  
  
    -   <span data-ttu-id="7f4dc-122">Nombre y la ubicación del ensamblado de interoperabilidad de destino</span><span class="sxs-lookup"><span data-stu-id="7f4dc-122">Name and location of the target interop assembly</span></span>  
  
     <span data-ttu-id="7f4dc-123">El siguiente fragmento de código muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7f4dc-123">The following code provides an example:</span></span>  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     <span data-ttu-id="7f4dc-124">Puede utilizar Tlbimp para crear ensamblados de interoperabilidad para bibliotecas de tipos, incluso para los objetos COM no registrados.</span><span class="sxs-lookup"><span data-stu-id="7f4dc-124">You can use Tlbimp to create interop assemblies for type libraries, even for unregistered COM objects.</span></span> <span data-ttu-id="7f4dc-125">Sin embargo, los objetos COM que hace referencia a ensamblados de interoperabilidad deben registrarse correctamente en el equipo donde va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="7f4dc-125">However, the COM objects referred to by interop assemblies must be properly registered on the computer where they are to be used.</span></span> <span data-ttu-id="7f4dc-126">Puede registrar un objeto COM mediante la utilidad Regsvr32 incluida con el sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="7f4dc-126">You can register a COM object by using the Regsvr32 utility included with the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f4dc-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f4dc-127">See also</span></span>

- [<span data-ttu-id="7f4dc-128">Interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="7f4dc-128">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
- [<span data-ttu-id="7f4dc-129">TlbImp.exe (Importador de la biblioteca de tipos)</span><span class="sxs-lookup"><span data-stu-id="7f4dc-129">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [<span data-ttu-id="7f4dc-130">Tlbexp.exe (Exportador de la biblioteca de tipos)</span><span class="sxs-lookup"><span data-stu-id="7f4dc-130">Tlbexp.exe (Type Library Exporter)</span></span>](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [<span data-ttu-id="7f4dc-131">Tutorial: Implementar la herencia mediante objetos COM</span><span class="sxs-lookup"><span data-stu-id="7f4dc-131">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [<span data-ttu-id="7f4dc-132">Solución de problemas de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="7f4dc-132">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
- [<span data-ttu-id="7f4dc-133">Imports (instrucción), espacio de nombres y tipo .NET</span><span class="sxs-lookup"><span data-stu-id="7f4dc-133">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
