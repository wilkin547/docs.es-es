---
title: 'Procedimiento Utilizar el espacio de nombres My: Guía de programación de C#'
description: Aprenda a usar el espacio de nombres "My". El espacio de nombres "My" proporciona acceso sencillo e intuitivo a varias clases de .NET.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, My namespace access
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
ms.openlocfilehash: 7abd5049a979d5a15d123052cba0cfdb35bf3fb7
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381715"
---
# <a name="how-to-use-the-my-namespace-c-programming-guide"></a><span data-ttu-id="6a425-104">Procedimiento Utilizar el espacio de nombres My (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="6a425-104">How to use the My namespace (C# Programming Guide)</span></span>

<span data-ttu-id="6a425-105">El espacio de nombres <xref:Microsoft.VisualBasic.MyServices> (`My` en Visual Basic) proporciona acceso fácil e intuitivo a una serie de clases de .NET, lo que le permite escribir código que interactúe con el equipo, la aplicación, la configuración, los recursos, etc.</span><span class="sxs-lookup"><span data-stu-id="6a425-105">The <xref:Microsoft.VisualBasic.MyServices> namespace (`My` in Visual Basic) provides easy and intuitive access to a number of .NET classes, enabling you to write code that interacts with the computer, application, settings, resources, and so on.</span></span> <span data-ttu-id="6a425-106">Aunque se diseñó originalmente para usarse con Visual Basic, el espacio de nombres `MyServices` puede usarse en aplicaciones de C#.</span><span class="sxs-lookup"><span data-stu-id="6a425-106">Although originally designed for use with Visual Basic, the `MyServices` namespace can be used in C# applications.</span></span>  
  
 <span data-ttu-id="6a425-107">Para obtener más información sobre el uso del espacio de nombres `MyServices` de Visual Basic, consulte [Desarrollo con My](../../../visual-basic/developing-apps/development-with-my/index.md).</span><span class="sxs-lookup"><span data-stu-id="6a425-107">For more information about using the `MyServices` namespace from Visual Basic, see [Development with My](../../../visual-basic/developing-apps/development-with-my/index.md).</span></span>  
  
## <a name="add-a-reference"></a><span data-ttu-id="6a425-108">Agregar una referencia</span><span class="sxs-lookup"><span data-stu-id="6a425-108">Add a reference</span></span>

 <span data-ttu-id="6a425-109">Para poder usar las clases `MyServices` en la solución, debe agregar una referencia a la biblioteca de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6a425-109">Before you can use the `MyServices` classes in your solution, you must add a reference to the Visual Basic library.</span></span>  
  
### <a name="add-a-reference-to-the-visual-basic-library"></a><span data-ttu-id="6a425-110">Cómo agregar una referencia a la biblioteca de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6a425-110">Add a reference to the Visual Basic library</span></span>  
  
1. <span data-ttu-id="6a425-111">En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Referencias** y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="6a425-111">In **Solution Explorer**, right-click the **References** node, and select **Add Reference**.</span></span>  
  
2. <span data-ttu-id="6a425-112">Cuando aparezca el cuadro de diálogo **Referencias**, desplácese hacia abajo en la lista y seleccione Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="6a425-112">When the **References** dialog box appears, scroll down the list, and select Microsoft.VisualBasic.dll.</span></span>  
  
     <span data-ttu-id="6a425-113">También es posible que quiera incluir la siguiente línea en la sección `using` al principio del programa.</span><span class="sxs-lookup"><span data-stu-id="6a425-113">You might also want to include the following line in the `using` section at the start of your program.</span></span>  
  
     [!code-csharp[csProgGuideNamespaces#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#18)]  
  
## <a name="example"></a><span data-ttu-id="6a425-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6a425-114">Example</span></span>  
 <span data-ttu-id="6a425-115">En este ejemplo, se llama a distintos métodos estáticos contenidos en el espacio de nombres `MyServices`.</span><span class="sxs-lookup"><span data-stu-id="6a425-115">This example calls various static methods contained in the `MyServices` namespace.</span></span> <span data-ttu-id="6a425-116">Para que pueda compilar este código, debe agregarse al proyecto una referencia a Microsoft.VisualBasic.DLL.</span><span class="sxs-lookup"><span data-stu-id="6a425-116">For this code to compile, a reference to Microsoft.VisualBasic.DLL must be added to the project.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#19)]  
  
 <span data-ttu-id="6a425-117">No se puede llamar a todas las clases en el espacio de nombres `MyServices` desde una aplicación de C#: por ejemplo, la clase <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy> no es compatible.</span><span class="sxs-lookup"><span data-stu-id="6a425-117">Not all the classes in the `MyServices` namespace can be called from a C# application: for example, the <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy> class is not compatible.</span></span> <span data-ttu-id="6a425-118">En este caso concreto, los métodos estáticos que forman parte de <xref:Microsoft.VisualBasic.FileIO.FileSystem>, que también se incluyen en el archivo VisualBasic.dll, pueden usarse en su lugar.</span><span class="sxs-lookup"><span data-stu-id="6a425-118">In this particular case, the static methods that are part of <xref:Microsoft.VisualBasic.FileIO.FileSystem>, which are also contained in VisualBasic.dll, can be used instead.</span></span> <span data-ttu-id="6a425-119">Por ejemplo, aquí se muestra cómo usar uno de estos métodos para duplicar un directorio:</span><span class="sxs-lookup"><span data-stu-id="6a425-119">For example, here is how to use one such method to duplicate a directory:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#20)]  
  
## <a name="see-also"></a><span data-ttu-id="6a425-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a425-120">See also</span></span>

- [<span data-ttu-id="6a425-121">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6a425-121">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6a425-122">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="6a425-122">Namespaces</span></span>](./index.md)
- [<span data-ttu-id="6a425-123">Utilizar espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="6a425-123">Using Namespaces</span></span>](./using-namespaces.md)
