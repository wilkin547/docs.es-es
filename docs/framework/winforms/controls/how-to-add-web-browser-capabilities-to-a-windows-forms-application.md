---
title: Agregar funcionalidades del explorador Web a la aplicación
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
ms.openlocfilehash: 7cb789121f4aa9a1e7cef54f992d0697ce6dfc62
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543578"
---
# <a name="how-to-add-web-browser-capabilities-to-a-windows-forms-application"></a>Cómo agregar funcionalidades del explorador Web a una aplicación Windows Forms

Con el control <xref:System.Windows.Forms.WebBrowser>, puede agregar funcionalidades del explorador web a la aplicación. De forma predeterminada, el control funciona como un explorador web. Después de cargar una dirección URL inicial estableciendo la propiedad <xref:System.Windows.Forms.WebBrowser.Url%2A>, puede navegar haciendo clic en hipervínculos o utilizando métodos abreviados de teclado para avanzar y retroceder por el historial de navegación. De forma predeterminada, puede acceder a funcionalidades adicionales del explorador a través del menú contextual. También puede abrir documentos nuevos colocándolos en el control. El control <xref:System.Windows.Forms.WebBrowser> también tiene varias propiedades, métodos y eventos que puede utilizar para implementar características de interfaz de usuario similares a las que se encuentran en Internet Explorer.

En el ejemplo de código siguiente, se implementa una barra de direcciones, los botones de exploración típicos, un menú **Archivo**, una barra de estado y una barra de título que muestra el título de la página actual.

## <a name="example"></a>Ejemplo

[!code-cpp[System.Windows.Forms.WebBrowser#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CPP/form1.cpp#0)]
[!code-csharp[System.Windows.Forms.WebBrowser#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CS/form1.cs#0)]
[!code-vb[System.Windows.Forms.WebBrowser#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/VB/form1.vb#0)]
  
## <a name="compile-the-code"></a>Compilar el código

Para este ejemplo se necesita:

- Referencias a los ensamblados `System`, `System.Drawing` y `System.Windows.Forms`.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.WebBrowser>
- [WebBrowser (control)](webbrowser-control-windows-forms.md)
