---
title: "Cómo: Utilizar el espacio de nombres My (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, My namespace access
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 56577ff61c3f637c8e5a0969ae75d65d24ddaef7
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-the-my-namespace-c-programming-guide"></a><span data-ttu-id="264f6-102">Cómo: Utilizar el espacio de nombres My (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="264f6-102">How to: Use the My Namespace (C# Programming Guide)</span></span>
<span data-ttu-id="264f6-103">El espacio de nombres <xref:Microsoft.VisualBasic.MyServices> (`My` en Visual Basic) proporciona acceso fácil e intuitivo a una serie de clases de .NET Framework, lo que le permite escribir código que interactúe con el equipo, la aplicación, la configuración, los recursos, etc.</span><span class="sxs-lookup"><span data-stu-id="264f6-103">The <xref:Microsoft.VisualBasic.MyServices> namespace (`My` in Visual Basic) provides easy and intuitive access to a number of .NET Framework classes, enabling you to write code that interacts with the computer, application, settings, resources, and so on.</span></span> <span data-ttu-id="264f6-104">Aunque se diseñó originalmente para usarse con Visual Basic, el espacio de nombres `MyServices` puede usarse en aplicaciones de C#.</span><span class="sxs-lookup"><span data-stu-id="264f6-104">Although originally designed for use with Visual Basic, the `MyServices` namespace can be used in C# applications.</span></span>  
  
 <span data-ttu-id="264f6-105">Para obtener más información sobre el uso del espacio de nombres `MyServices` de Visual Basic, consulte [Development with My](../../../visual-basic/developing-apps/development-with-my/index.md) (Desarrollo con My).</span><span class="sxs-lookup"><span data-stu-id="264f6-105">For more information about using the `MyServices` namespace from Visual Basic, see [Development with My](../../../visual-basic/developing-apps/development-with-my/index.md).</span></span>  
  
## <a name="adding-a-reference"></a><span data-ttu-id="264f6-106">Agregar una referencia</span><span class="sxs-lookup"><span data-stu-id="264f6-106">Adding a Reference</span></span>  
 <span data-ttu-id="264f6-107">Para poder usar las clases `MyServices` en la solución, debe agregar una referencia a la biblioteca de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="264f6-107">Before you can use the `MyServices` classes in your solution, you must add a reference to the Visual Basic library.</span></span>  
  
#### <a name="to-add-a-reference-to-the-visual-basic-library"></a><span data-ttu-id="264f6-108">Para agregar una referencia a la biblioteca de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="264f6-108">To add a reference to the Visual Basic library</span></span>  
  
1.  <span data-ttu-id="264f6-109">En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Referencias** y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="264f6-109">In **Solution Explorer**, right-click the **References** node, and select **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="264f6-110">Cuando aparezca el cuadro de diálogo **Referencias**, desplácese hacia abajo en la lista y seleccione Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="264f6-110">When the **References** dialog box appears, scroll down the list, and select Microsoft.VisualBasic.dll.</span></span>  
  
     <span data-ttu-id="264f6-111">También es posible que quiera incluir la siguiente línea en la sección `using` al principio del programa.</span><span class="sxs-lookup"><span data-stu-id="264f6-111">You might also want to include the following line in the `using` section at the start of your program.</span></span>  
  
     <span data-ttu-id="264f6-112">[!code-cs[csProgGuideNamespaces#18](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="264f6-112">[!code-cs[csProgGuideNamespaces#18](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="264f6-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="264f6-113">Example</span></span>  
 <span data-ttu-id="264f6-114">En este ejemplo, se llama a distintos métodos estáticos contenidos en el espacio de nombres `MyServices`.</span><span class="sxs-lookup"><span data-stu-id="264f6-114">This example calls various static methods contained in the `MyServices` namespace.</span></span> <span data-ttu-id="264f6-115">Para que pueda compilar este código, debe agregarse al proyecto una referencia a Microsoft.VisualBasic.DLL.</span><span class="sxs-lookup"><span data-stu-id="264f6-115">For this code to compile, a reference to Microsoft.VisualBasic.DLL must be added to the project.</span></span>  
  
 <span data-ttu-id="264f6-116">[!code-cs[csProgGuideNamespaces#19](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="264f6-116">[!code-cs[csProgGuideNamespaces#19](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_2.cs)]</span></span>  
  
 <span data-ttu-id="264f6-117">No se puede llamar a todas las clases en el espacio de nombres `MyServices` desde una aplicación de C#: por ejemplo, la clase <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy> no es compatible.</span><span class="sxs-lookup"><span data-stu-id="264f6-117">Not all the classes in the `MyServices` namespace can be called from a C# application: for example, the <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy> class is not compatible.</span></span> <span data-ttu-id="264f6-118">En este caso concreto, los métodos estáticos que forman parte de <xref:Microsoft.VisualBasic.FileIO.FileSystem>, que también se incluyen en el archivo VisualBasic.dll, pueden usarse en su lugar.</span><span class="sxs-lookup"><span data-stu-id="264f6-118">In this particular case, the static methods that are part of <xref:Microsoft.VisualBasic.FileIO.FileSystem>, which are also contained in VisualBasic.dll, can be used instead.</span></span> <span data-ttu-id="264f6-119">Por ejemplo, aquí se muestra cómo usar uno de estos métodos para duplicar un directorio:</span><span class="sxs-lookup"><span data-stu-id="264f6-119">For example, here is how to use one such method to duplicate a directory:</span></span>  
  
 <span data-ttu-id="264f6-120">[!code-cs[csProgGuideNamespaces#20](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="264f6-120">[!code-cs[csProgGuideNamespaces#20](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="264f6-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="264f6-121">See Also</span></span>  
 <span data-ttu-id="264f6-122">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="264f6-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="264f6-123">[Namespaces](../../../csharp/programming-guide/namespaces/index.md)  (Espacios de nombres)</span><span class="sxs-lookup"><span data-stu-id="264f6-123">[Namespaces](../../../csharp/programming-guide/namespaces/index.md) </span></span>  
 [<span data-ttu-id="264f6-124">Utilizar espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="264f6-124">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)

