---
title: 'Procedimiento Utilizar el espacio de nombres My: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, My namespace access
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
ms.openlocfilehash: 063b46a32ced859c6c86e40c4a6b9870c3decd24
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75700424"
---
# <a name="how-to-use-the-my-namespace-c-programming-guide"></a>Procedimiento Utilizar el espacio de nombres My (Guía de programación de C#)
El espacio de nombres <xref:Microsoft.VisualBasic.MyServices> (`My` en Visual Basic) proporciona acceso fácil e intuitivo a una serie de clases de .NET Framework, lo que le permite escribir código que interactúe con el equipo, la aplicación, la configuración, los recursos, etc. Aunque se diseñó originalmente para usarse con Visual Basic, el espacio de nombres `MyServices` puede usarse en aplicaciones de C#.  
  
 Para obtener más información sobre el uso del espacio de nombres `MyServices` de Visual Basic, consulte [Desarrollo con My](../../../visual-basic/developing-apps/development-with-my/index.md).  
  
## <a name="adding-a-reference"></a>Agregar una referencia  
 Para poder usar las clases `MyServices` en la solución, debe agregar una referencia a la biblioteca de Visual Basic.  
  
#### <a name="to-add-a-reference-to-the-visual-basic-library"></a>Para agregar una referencia a la biblioteca de Visual Basic  
  
1. En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Referencias** y seleccione **Agregar referencia**.  
  
2. Cuando aparezca el cuadro de diálogo **Referencias**, desplácese hacia abajo en la lista y seleccione Microsoft.VisualBasic.dll.  
  
     También es posible que quiera incluir la siguiente línea en la sección `using` al principio del programa.  
  
     [!code-csharp[csProgGuideNamespaces#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#18)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, se llama a distintos métodos estáticos contenidos en el espacio de nombres `MyServices`. Para que pueda compilar este código, debe agregarse al proyecto una referencia a Microsoft.VisualBasic.DLL.  
  
 [!code-csharp[csProgGuideNamespaces#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#19)]  
  
 No se puede llamar a todas las clases en el espacio de nombres `MyServices` desde una aplicación de C#: por ejemplo, la clase <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy> no es compatible. En este caso concreto, los métodos estáticos que forman parte de <xref:Microsoft.VisualBasic.FileIO.FileSystem>, que también se incluyen en el archivo VisualBasic.dll, pueden usarse en su lugar. Por ejemplo, aquí se muestra cómo usar uno de estos métodos para duplicar un directorio:  
  
 [!code-csharp[csProgGuideNamespaces#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#20)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Espacios de nombres](./index.md)
- [Utilizar espacios de nombres](./using-namespaces.md)
