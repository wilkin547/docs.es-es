---
description: 'Más información acerca de cómo: hacer referencia a objetos COM desde Visual Basic'
title: 'Cómo: Hacer referencia a objetos COM desde Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
ms.openlocfilehash: f0c08e5be9144bdefc3fe0b4609bad2421889d52
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100477572"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a><span data-ttu-id="90a62-103">Cómo: Hacer referencia a objetos COM desde Visual Basic</span><span class="sxs-lookup"><span data-stu-id="90a62-103">How to: Reference COM Objects from Visual Basic</span></span>

<span data-ttu-id="90a62-104">En Visual Basic, la adición de referencias a objetos COM que tienen bibliotecas de tipos requiere la creación de un ensamblado de interoperabilidad para la biblioteca COM.</span><span class="sxs-lookup"><span data-stu-id="90a62-104">In Visual Basic, adding references to COM objects that have type libraries requires the creation of an interop assembly for the COM library.</span></span> <span data-ttu-id="90a62-105">Las referencias a los miembros del objeto COM se enrutan al ensamblado de interoperabilidad y, a continuación, se reenvían al objeto COM real.</span><span class="sxs-lookup"><span data-stu-id="90a62-105">References to the members of the COM object are routed to the interop assembly and then forwarded to the actual COM object.</span></span> <span data-ttu-id="90a62-106">Las respuestas del objeto COM se enrutan al ensamblado de interoperabilidad y se reenvían a la aplicación .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="90a62-106">Responses from the COM object are routed to the interop assembly and forwarded to your .NET Framework application.</span></span>  
  
 <span data-ttu-id="90a62-107">Puede hacer referencia a un objeto COM sin utilizar un ensamblado de interoperabilidad incrustando la información de tipo para el objeto COM en un ensamblado .NET.</span><span class="sxs-lookup"><span data-stu-id="90a62-107">You can reference a COM object without using an interop assembly by embedding the type information for the COM object in a .NET assembly.</span></span> <span data-ttu-id="90a62-108">Para insertar información de tipo, establezca la `Embed Interop Types` propiedad en `True` para la referencia al objeto com.</span><span class="sxs-lookup"><span data-stu-id="90a62-108">To embed type information, set the `Embed Interop Types` property to `True` for the reference to the COM object.</span></span> <span data-ttu-id="90a62-109">Si va a compilar mediante el compilador de línea de comandos, use la `/link` opción para hacer referencia a la biblioteca com.</span><span class="sxs-lookup"><span data-stu-id="90a62-109">If you are compiling by using the command-line compiler, use the `/link` option to reference the COM library.</span></span> <span data-ttu-id="90a62-110">Para obtener más información, vea [-Link (Visual Basic)](../../reference/command-line-compiler/link.md).</span><span class="sxs-lookup"><span data-stu-id="90a62-110">For more information, see [-link (Visual Basic)](../../reference/command-line-compiler/link.md).</span></span>  
  
 <span data-ttu-id="90a62-111">Visual Basic crea automáticamente ensamblados de interoperabilidad al agregar una referencia a una biblioteca de tipos desde el entorno de desarrollo integrado (IDE).</span><span class="sxs-lookup"><span data-stu-id="90a62-111">Visual Basic automatically creates interop assemblies when you add a reference to a type library from the integrated development environment (IDE).</span></span> <span data-ttu-id="90a62-112">Al trabajar desde la línea de comandos, puede usar la utilidad TlbImp para crear manualmente ensamblados de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="90a62-112">When working from the command line, you can use the Tlbimp utility to manually create interop assemblies.</span></span>  
  
### <a name="to-add-references-to-com-objects"></a><span data-ttu-id="90a62-113">Para agregar referencias a objetos COM</span><span class="sxs-lookup"><span data-stu-id="90a62-113">To add references to COM objects</span></span>  
  
1. <span data-ttu-id="90a62-114">En el menú **proyecto** , elija **Agregar referencia** y, a continuación, haga clic en la pestaña **com** del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="90a62-114">On the **Project** menu, choose **Add Reference** and then click the **COM** tab in the dialog box.</span></span>  
  
2. <span data-ttu-id="90a62-115">Seleccione el componente que desea usar en la lista de objetos COM.</span><span class="sxs-lookup"><span data-stu-id="90a62-115">Select the component you want to use from the list of COM objects.</span></span>  
  
3. <span data-ttu-id="90a62-116">Para simplificar el acceso al ensamblado de interoperabilidad, agregue una `Imports` instrucción a la parte superior de la clase o módulo en el que va a usar el objeto com.</span><span class="sxs-lookup"><span data-stu-id="90a62-116">To simplify access to the interop assembly, add an `Imports` statement to the top of the class or module in which you will use the COM object.</span></span> <span data-ttu-id="90a62-117">Por ejemplo, en el ejemplo de código siguiente se importa el espacio `INKEDLib` de nombres para los objetos a los que se hace referencia en la `Microsoft InkEdit Control 1.0` biblioteca.</span><span class="sxs-lookup"><span data-stu-id="90a62-117">For example, the following code example imports the namespace `INKEDLib` for objects referenced in the `Microsoft InkEdit Control 1.0` library.</span></span>  
  
     [!code-vb[VbVbalrInterop#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#40)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a><span data-ttu-id="90a62-118">Para crear un ensamblado de interoperabilidad mediante Tlbimp</span><span class="sxs-lookup"><span data-stu-id="90a62-118">To create an interop assembly using Tlbimp</span></span>  
  
1. <span data-ttu-id="90a62-119">Agregue la ubicación de Tlbimp a la ruta de búsqueda, si aún no forma parte de la ruta de acceso de búsqueda y no está actualmente en el directorio donde se encuentra.</span><span class="sxs-lookup"><span data-stu-id="90a62-119">Add the location of Tlbimp to the search path, if it is not already part of the search path and you are not currently in the directory where it is located.</span></span>  
  
2. <span data-ttu-id="90a62-120">Llame a Tlbimp desde un símbolo del sistema y proporcione la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="90a62-120">Call Tlbimp from a command prompt, providing the following information:</span></span>  
  
    - <span data-ttu-id="90a62-121">Nombre y ubicación de la DLL que contiene la biblioteca de tipos</span><span class="sxs-lookup"><span data-stu-id="90a62-121">Name and location of the DLL that contains the type library</span></span>  
  
    - <span data-ttu-id="90a62-122">Nombre y ubicación del espacio de nombres donde se debe colocar la información</span><span class="sxs-lookup"><span data-stu-id="90a62-122">Name and location of the namespace where the information should be placed</span></span>  
  
    - <span data-ttu-id="90a62-123">Nombre y ubicación del ensamblado de interoperabilidad de destino</span><span class="sxs-lookup"><span data-stu-id="90a62-123">Name and location of the target interop assembly</span></span>  
  
     <span data-ttu-id="90a62-124">El siguiente fragmento de código muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="90a62-124">The following code provides an example:</span></span>  
  
    ```console  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     <span data-ttu-id="90a62-125">Puede usar TlbImp para crear ensamblados de interoperabilidad para bibliotecas de tipos, incluso para objetos COM no registrados.</span><span class="sxs-lookup"><span data-stu-id="90a62-125">You can use Tlbimp to create interop assemblies for type libraries, even for unregistered COM objects.</span></span> <span data-ttu-id="90a62-126">Sin embargo, los objetos COM a los que hacen referencia los ensamblados de interoperabilidad deben estar registrados correctamente en el equipo en el que se van a utilizar.</span><span class="sxs-lookup"><span data-stu-id="90a62-126">However, the COM objects referred to by interop assemblies must be properly registered on the computer where they are to be used.</span></span> <span data-ttu-id="90a62-127">Puede registrar un objeto COM mediante la utilidad regsvr32 incluida en el sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="90a62-127">You can register a COM object by using the Regsvr32 utility included with the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90a62-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="90a62-128">See also</span></span>

- [<span data-ttu-id="90a62-129">Interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="90a62-129">COM Interop</span></span>](index.md)
- [<span data-ttu-id="90a62-130">TlbImp.exe (Importador de la biblioteca de tipos)</span><span class="sxs-lookup"><span data-stu-id="90a62-130">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [<span data-ttu-id="90a62-131">Tlbexp.exe (Exportador de la biblioteca de tipos)</span><span class="sxs-lookup"><span data-stu-id="90a62-131">Tlbexp.exe (Type Library Exporter)</span></span>](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [<span data-ttu-id="90a62-132">Tutorial: Implementación de la herencia mediante objetos COM</span><span class="sxs-lookup"><span data-stu-id="90a62-132">Walkthrough: Implementing Inheritance with COM Objects</span></span>](walkthrough-implementing-inheritance-with-com-objects.md)
- [<span data-ttu-id="90a62-133">Solución de problemas de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="90a62-133">Troubleshooting Interoperability</span></span>](troubleshooting-interoperability.md)
- [<span data-ttu-id="90a62-134">Instrucción Imports (Tipo y espacio de nombres de .NET)</span><span class="sxs-lookup"><span data-stu-id="90a62-134">Imports Statement (.NET Namespace and Type)</span></span>](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
