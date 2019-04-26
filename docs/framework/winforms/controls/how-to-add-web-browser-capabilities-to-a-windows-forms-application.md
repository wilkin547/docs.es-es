---
title: Procedimiento para agregar funcionalidades de explorador web a una aplicación de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- WebBrowser control [Windows Forms], adding Web browser capabilities to your application
- WebBrowser control [Windows Forms], examples
- Web browsers [.NET Framework], adding to Windows Forms
- examples [Windows Forms], WebBrowser control
- Windows Forms, adding Web browser functionality
ms.assetid: 3871f072-b57a-435b-9976-e5da28df04a7
ms.openlocfilehash: 29422ad384240b017b279795d07e3c8100fae493
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011065"
---
# <a name="how-to-add-web-browser-capabilities-to-a-windows-forms-application"></a>Procedimiento para agregar funcionalidades de explorador web a una aplicación de formularios Windows Forms
Con el control <xref:System.Windows.Forms.WebBrowser>, puede agregar funcionalidades del explorador web a la aplicación. De forma predeterminada, el control funciona como un explorador web. Después de cargar una dirección URL inicial estableciendo la propiedad <xref:System.Windows.Forms.WebBrowser.Url%2A>, puede navegar haciendo clic en hipervínculos o utilizando métodos abreviados de teclado para avanzar y retroceder por el historial de navegación. De forma predeterminada, puede acceder a funcionalidades adicionales del explorador a través del menú contextual. También puede abrir documentos nuevos colocándolos en el control. El control <xref:System.Windows.Forms.WebBrowser> también tiene varias propiedades, métodos y eventos que puede utilizar para implementar características de interfaz de usuario similares a las que se encuentran en Internet Explorer.  
  
 En el ejemplo de código siguiente, se implementa una barra de direcciones, los botones de exploración típicos, un menú **Archivo**, una barra de estado y una barra de título que muestra el título de la página actual.  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[System.Windows.Forms.WebBrowser#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CPP/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.WebBrowser#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.WebBrowser#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados `System`, `System.Drawing` y `System.Windows.Forms`.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.WebBrowser>
- [WebBrowser (control)](webbrowser-control-windows-forms.md)
