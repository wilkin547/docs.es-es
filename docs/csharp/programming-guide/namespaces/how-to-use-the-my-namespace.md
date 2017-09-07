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
# <a name="how-to-use-the-my-namespace-c-programming-guide"></a>Cómo: Utilizar el espacio de nombres My (Guía de programación de C#)
El espacio de nombres <xref:Microsoft.VisualBasic.MyServices> (`My` en Visual Basic) proporciona acceso fácil e intuitivo a una serie de clases de .NET Framework, lo que le permite escribir código que interactúe con el equipo, la aplicación, la configuración, los recursos, etc. Aunque se diseñó originalmente para usarse con Visual Basic, el espacio de nombres `MyServices` puede usarse en aplicaciones de C#.  
  
 Para obtener más información sobre el uso del espacio de nombres `MyServices` de Visual Basic, consulte [Development with My](../../../visual-basic/developing-apps/development-with-my/index.md) (Desarrollo con My).  
  
## <a name="adding-a-reference"></a>Agregar una referencia  
 Para poder usar las clases `MyServices` en la solución, debe agregar una referencia a la biblioteca de Visual Basic.  
  
#### <a name="to-add-a-reference-to-the-visual-basic-library"></a>Para agregar una referencia a la biblioteca de Visual Basic  
  
1.  En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Referencias** y seleccione **Agregar referencia**.  
  
2.  Cuando aparezca el cuadro de diálogo **Referencias**, desplácese hacia abajo en la lista y seleccione Microsoft.VisualBasic.dll.  
  
     También es posible que quiera incluir la siguiente línea en la sección `using` al principio del programa.  
  
     [!code-cs[csProgGuideNamespaces#18](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, se llama a distintos métodos estáticos contenidos en el espacio de nombres `MyServices`. Para que pueda compilar este código, debe agregarse al proyecto una referencia a Microsoft.VisualBasic.DLL.  
  
 [!code-cs[csProgGuideNamespaces#19](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_2.cs)]  
  
 No se puede llamar a todas las clases en el espacio de nombres `MyServices` desde una aplicación de C#: por ejemplo, la clase <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy> no es compatible. En este caso concreto, los métodos estáticos que forman parte de <xref:Microsoft.VisualBasic.FileIO.FileSystem>, que también se incluyen en el archivo VisualBasic.dll, pueden usarse en su lugar. Por ejemplo, aquí se muestra cómo usar uno de estos métodos para duplicar un directorio:  
  
 [!code-cs[csProgGuideNamespaces#20](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-my-namespace_3.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Namespaces](../../../csharp/programming-guide/namespaces/index.md)  (Espacios de nombres)  
 [Utilizar espacios de nombres](../../../csharp/programming-guide/namespaces/using-namespaces.md)

