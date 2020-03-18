---
title: Crear el documento de origen de Office Open XML (C#)
ms.date: 07/20/2015
ms.assetid: 653c8cdb-73be-4dc2-927f-924cfb4ed9ed
ms.openlocfilehash: d6c4d8866bba58e86735099a62041894a9faa9b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "70204160"
---
# <a name="creating-the-source-office-open-xml-document-c"></a>Crear el documento de origen de Office Open XML (C#)

En este tema se muestra cómo crear el documento WordprocessingML XML abierto de Office que usan los otros ejemplos de este tutorial. Si sigue estas instrucciones, su resultado coincidirá con el resultado proporcionado en cada ejemplo.

No obstante, los ejemplos de este tutorial funcionarán con cualquier documento WordprocessingML válido.

Para crear el documento que se usa en este tutorial, debe tener Microsoft Office 2007 o posterior instalado o bien tener Microsoft Office 2003 con el paquete de compatibilidad de Microsoft Office para formatos de archivo de Word, Excel y PowerPoint 2007.

## <a name="creating-the-wordprocessingml-document"></a>Crear el documento WordprocessingML

#### <a name="to-create-the-wordprocessingml-document"></a>Para crear el documento WordprocessingML

1. Cree un nuevo documento de Microsoft Word.

2. Pegue el siguiente texto en el nuevo documento:

    ```text
    Parsing WordprocessingML with LINQ to XML

    The following example prints to the console.

    using System;

    class Program {
        public static void Main(string[] args) {
            Console.WriteLine("Hello World");
        }
    }

    This example produces the following output:

    Hello World
    ```

3. Dé formato a la primera línea con el estilo "Título 1".

4. Seleccione las líneas que contienen el código C#. La primera línea empieza con la palabra clave `using`. La última línea es la última llave de cierre. Dé formato a las líneas con la fuente Courier. Déles formato con un nuevo estilo y llame a ese nuevo estilo "Code".

5. Finalmente, seleccione toda la línea que contiene el resultado y déle formato con el estilo `Code`.

6. Guarde el documento y déle el nombre SampleDoc.docx.

    > [!NOTE]
    > Si está usando Microsoft Word 2003, seleccione **Documento de Word 2007** en la lista desplegable **Guardar como tipo**.
