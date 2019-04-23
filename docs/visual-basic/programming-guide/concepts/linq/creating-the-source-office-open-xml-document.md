---
title: Crear el documento de origen Office Open XML (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 61ccd6fb-0c47-4075-afdf-5b5021330f21
ms.openlocfilehash: 83cb7d0a325e11c9669f1331e57bed7bf09f27c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59333696"
---
# <a name="creating-the-source-office-open-xml-document-visual-basic"></a>Crear el documento de origen Office Open XML (Visual Basic)
En este tema se muestra cómo crear el documento WordprocessingML XML abierto de Office que usan los otros ejemplos de este tutorial. Si sigue estas instrucciones, su resultado coincidirá con el resultado proporcionado en cada ejemplo.  
  
 No obstante, los ejemplos de este tutorial funcionarán con cualquier documento WordprocessingML válido.  
  
 Para crear el documento que se usa en este tutorial, debe tener Microsoft Office 2007 o posterior instalado o bien tener Microsoft Office 2003 con el paquete de compatibilidad de Microsoft Office para formatos de archivo de Word, Excel y PowerPoint 2007.  
  
## <a name="creating-the-wordprocessingml-document"></a>Crear el documento WordprocessingML  
  
#### <a name="to-create-the-wordprocessingml-document"></a>Para crear el documento WordprocessingML  
  
1. Cree un nuevo documento de Microsoft Word.  
  
2. Pegue el siguiente texto en el nuevo documento:  
  
    ```  
    Parsing WordprocessingML with LINQ to XML  
  
    The following example prints to the console.  
  
    Imports System  
  
    Class Program  
        Public Shared  Sub Main(ByVal args() As String)  
            Console.WriteLine("Hello World")  
        End Sub  
    End Class  
  
    This example produces the following output:  
  
    Hello World  
    ```  
  
3. Dé formato a la primera línea con el estilo "Título 1".  
  
4. Seleccione las líneas que contienen el código de Visual Basic. La primera línea empieza con la palabra clave `Imports`. La última línea es "End Class". Dé formato a las líneas con la fuente Courier. Déles formato con un nuevo estilo y llame a ese nuevo estilo "Code".  
  
5. Finalmente, seleccione toda la línea que contiene el resultado y déle formato con el estilo `Code`.  
  
6. Guarde el documento y déle el nombre SampleDoc.docx.  
  
    > [!NOTE]
    >  Si está usando Microsoft Word 2003, seleccione **Documento de Word 2007** en la lista desplegable **Guardar como tipo**.  
  
## <a name="see-also"></a>Vea también

- [Tutorial: Manipular contenido en un documento WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
