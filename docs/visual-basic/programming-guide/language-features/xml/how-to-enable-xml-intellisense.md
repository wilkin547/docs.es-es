---
title: "Cómo: habilitar IntelliSense XML en Visual Basic | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML IntelliSense [Visual Basic]
- XML [Visual Basic], IntelliSense
- IntelliSense [Visual Basic], XML
ms.assetid: af67d0ee-a4a6-4abf-9c07-5a8cfe80d111
caps.latest.revision: 25
author: dotnet-bot
ms.author: dotnetcontent
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 84af19189fa3fc510c8d4f8e408cbb2a393d8b8f
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-enable-xml-intellisense-in-visual-basic"></a>Cómo: Habilitar IntelliSense XML en Visual Basic
XML IntelliSense en Visual Basic proporciona la finalización de palabras para los elementos que se definen en un esquema XML. Para habilitar IntelliSense XML en Visual Basic, debe hacer lo siguiente:  
  
1.  Obtenga el archivo de esquema (XSD) de XML o archivos para los archivos XML que leer o escribir en la aplicación.  
  
2.  Incluir los archivos de esquema XML en el proyecto.  
  
3.  Importar el espacio de nombres de destino o espacios de nombres en el archivo de código o proyecto. Un espacio de nombres de destino se identifica mediante el `targetNamespace` o `tns` atributo del esquema XSD.  
  
     Para importar un espacio de nombres de destino, utilice el `Imports` instrucción, o agregar un espacio de nombres para todos los archivos de código en un proyecto mediante la **referencias** página del Diseñador de proyectos.  
  
 Para obtener más información sobre las capacidades de IntelliSense XML en Visual Basic, consulte [IntelliSense XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md). Para obtener más información sobre la importación de espacios de nombres XML, vea [Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) o [página referencias, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
 ![vínculo a vídeo](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") para una versión en vídeo de este tema, consulte [vídeo acerca de cómo: habilitar IntelliSense XML en Visual Basic](http://go.microsoft.com/fwlink/?LinkId=102466). Para una demostración en vídeo relacionada, vea [¿cómo puedo Enable XML IntelliSense and Use XML Namespaces?](http://go.microsoft.com/fwlink/?LinkId=143035).  
  
## <a name="enable-xml-intellisense-in-visual-basic"></a>Habilitar IntelliSense XML en Visual Basic  
 Si tiene un archivo XML, pero no tiene un archivo de esquema XSD para él, en SP1 puede crear un archivo de esquema XSD utilizando el Asistente de XML a esquema. También se puede utilizar la inferencia de esquema en el Editor XML de Visual Studio.  
  
#### <a name="to-create-an-xsd-schema-file-for-an-xml-file-by-using-the-xml-to-schema-wizard-requires-sp1"></a>Para crear un archivo de esquema XSD para un archivo XML mediante el Asistente de XML a esquema (requiere SP1)  
  
1.  En el proyecto, haga clic en **Agregar nuevo elemento** en el **proyecto** menú.  
  
2.  Seleccione el **Xml a esquema** plantilla de elemento desde el **datos** o **elementos comunes** categorías de plantillas.  
  
3.  Proporcione un nombre de archivo para el archivo o archivos XSD que se almacenará en el conjunto de esquemas inferidos y, a continuación, haga clic en **agregar**.  
  
4.  En el **establecer deducir el esquema de XML de documentos XML** ventana, agregue uno o varios documentos XML para inferir el conjunto de esquemas XML.  
  
    -   Para agregar archivos de texto que contienen documentos XML mediante el Explorador de archivos, haga clic en **agregar desde archivo**.  
  
    -   Para agregar un documento XML desde una dirección HTTP, haga clic en **agregar desde Web**.  
  
    -   Para copiar o escribir el contenido de un documento XML en el asistente, haga clic en **escribir o pegar XML**.  
  
5.  Cuando haya especificado todos los orígenes de documento XML desde el que va a inferir el conjunto de esquemas XML, haga clic en **Aceptar** deducir el esquema XML establecido. El conjunto de esquemas se guarda en la carpeta del proyecto en uno o más archivos XSD. (Para cada espacio de nombres XML en el esquema, se crea un archivo).  
  
#### <a name="to-create-an-xsd-schema-file-for-an-xml-file-by-using-schema-inference-in-the-visual-studio-xml-editor"></a>Para crear un archivo de esquema XSD para un archivo XML utilizando la inferencia del esquema en el Editor XML de Visual Studio  
  
1.  Edite el archivo XML en el Diseñador de XML de Visual Studio.  
  
2.  Cuando el cursor está en algún lugar en el archivo XML, el **XML** aparece el menú. Haga clic en **Create Schema** en el **XML** menú. Se crea un archivo XSD del esquema XSD inferido del archivo XML.  
  
3.  Guarde el archivo de esquema XSD.  
  
    > [!NOTE]
    >  Los distintos esquemas XSD se podrían inferir de varios documentos XML que se piensa que tienen el mismo esquema. Esto puede ocurrir cuando se encuentran elementos y atributos concretos en un archivo XML y no en otro, o cuando se incluyen los elementos en un orden diferente, por ejemplo. Debe revisar los esquemas XSD deducidos son completos y precisos cuando se utiliza la inferencia del esquema XSD.  
  
#### <a name="to-include-an-xsd-schema-file"></a>Para incluir un archivo de esquema XSD  
  
-   De forma predeterminada, no puede ver archivos XSD en proyectos de Visual Basic. Si el archivo XSD ya está incluido en las carpetas del proyecto, haga clic en el **mostrar todos los archivos** botón **el Explorador de soluciones**. Busque el archivo XSD en **el Explorador de soluciones**, haga clic en el archivo y haga clic en **incluir el archivo en el proyecto**.  
  
-   Si el archivo XSD no es ya parte del proyecto, en **el Explorador de soluciones**, haga clic en la carpeta en la que desea almacenar el archivo XSD, seleccione **agregar**y, a continuación, haga clic en **elemento existente**. Busque el archivo XSD y, a continuación, haga clic en **agregar**.  
  
#### <a name="to-import-an-xml-namespace-in-a-code-file"></a>Para importar un espacio de nombres XML en un archivo de código  
  
1.  Identificar el espacio de nombres de destino del esquema XSD.  
  
2.  Al principio del archivo de código, agregue un `Imports` instrucción destino espacio de nombres XML, como se muestra en el ejemplo siguiente.  
  
     [!code-vb[1 VbXMLSamples](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_1.vb)]  
  
     Para importar un espacio de nombres XML como espacio de nombres predeterminado, es decir, el espacio de nombres que se aplica a elementos y atributos que no tienen un prefijo de espacio de nombres XML agrega un `Imports` instrucción para el espacio de nombres XML de destino predeterminado. No especifique un prefijo de espacio de nombres. Siguiente es un ejemplo de un `Imports` instrucción.  
  
     [!code-vb[VbXmlSamples&#50;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_2.vb)]  
  
#### <a name="to-import-an-xml-namespace-for-all-files-in-a-project"></a>Para importar un espacio de nombres XML para todos los archivos en un proyecto  
  
1.  Espacio de nombres XML importado en un archivo de código se aplica a ese archivo de código solo. Para importar un espacio de nombres XML que se aplica a todos los archivos de código en un proyecto, abra el Diseñador de proyectos haciendo doble clic en **mi proyecto** en **el Explorador de soluciones**.  
  
2.  En el **referencias** ficha el **espacios de nombres importados** , escriba el espacio de nombres XML en forma de una declaración de espacio de nombres XML completa (por ejemplo, `<xmlns: ns="http://sampleNamespace">`). Si el espacio de nombres XML no especifica un prefijo de espacio de nombres, el espacio de nombres será el espacio de nombres XML predeterminado para el proyecto.  
  
3.  Haga clic en **Agregar importación del usuario**.  
  
## <a name="see-also"></a>Vea también  
 [Imports (instrucción) (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [Página Referencias, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)   
 [XML IntelliSense en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)

