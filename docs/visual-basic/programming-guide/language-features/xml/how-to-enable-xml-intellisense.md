---
title: "C&#243;mo: Habilitar IntelliSense XML en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "IntelliSense [Visual Basic], XML"
  - "XML [Visual Basic], IntelliSense"
  - "XML IntelliSense [Visual Basic]"
ms.assetid: af67d0ee-a4a6-4abf-9c07-5a8cfe80d111
caps.latest.revision: 25
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 25
---
# C&#243;mo: Habilitar IntelliSense XML en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

IntelliSense XML en Visual Basic proporciona la finalización de la palabra de los elementos que se definen en un esquema XML.  Para habilitar IntelliSense XML en Visual Basic, debe seguir estos pasos:  
  
1.  Obtenga el archivo o archivos del esquema XML \(XSD\) para los archivos XML que leerá la aplicación o en los que escribirá.  
  
2.  Incluya los archivos del esquema XML en el proyecto.  
  
3.  Importe el espacio o espacios de nombres de destino en el archivo de código o proyecto.  Un espacio de nombres de destino se identifica mediante el atributo `targetNamespace` o `tns` del esquema XSD.  
  
     Para importar un espacio de nombres de destino, use la instrucción `Imports` o agregue un espacio de nombres para todos los archivos de código de un proyecto mediante la página **Referencias** del Diseñador de proyectos.  
  
 Para obtener más información sobre las funcionalidades de IntelliSense XML en Visual Basic, vea [IntelliSense XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md).  Para obtener más información sobre cómo importar espacios de nombres XML, vea [Imports \(Instrucción, Espacio de nombres XML\)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) o [Página Referencias, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic).  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
 ![vínculo a vídeo](../../../../csharp/programming-guide/concepts/linq/media/playvideo.png "PlayVideo") Para obtener una versión en vídeo de este tema, vea [Video How to: Enable XML IntelliSense in Visual Basic](http://go.microsoft.com/fwlink/?LinkId=102466).  Para obtener una demostración de vídeo relacionada, vea [How Do I Enable XML IntelliSense and Use XML Namespaces?](http://go.microsoft.com/fwlink/?LinkId=143035).  
  
## Habilitar IntelliSense XML en Visual Basic  
 Si tiene un archivo XML pero no tiene ningún archivo de esquema XSD para él, en SP1 puede crear un archivo de esquema XSD utilizando el Asistente de XML a esquema.  También puede utilizar la inferencia de esquema en el Editor XML de Visual Studio.  
  
#### Para crear un archivo de esquema XSD para un archivo XML utilizando el Asistente de XML a esquema \(se requiere SP1\)  
  
1.  En el proyecto, haga clic en **Agregar nuevo elemento** en el menú **Proyecto**.  
  
2.  Seleccione la plantilla de elementos **XML a esquema** en las categorías de plantilla **Datos** o **Elementos comunes**.  
  
3.  Proporcione un nombre de archivo para el archivo o archivos XSD en los que se almacenará el conjunto de esquemas inferidos y, a continuación, haga clic en **Agregar**.  
  
4.  En la ventana **Inferir conjunto de esquemas XML de documentos XML**, agregue uno o más documentos XML de los que inferirá el conjunto de esquemas XML.  
  
    -   Para agregar archivos de texto que contienen documentos XML mediante el Explorador del archivo, haga clic **Agregar desde archivo**.  
  
    -   Para agregar un documento XML desde una dirección HTTP, haga clic en **Agregar desde web**.  
  
    -   Para copiar o escribir el contenido de un documento XML en el asistente, haga clic en **Escribir o pegar XML**.  
  
5.  Una vez especificados todos los orígenes de documentos XML de los que desea inferir el conjunto de esquemas XML, haga clic en **Aceptar** para inferir el conjunto de esquemas XML.  El conjunto de esquemas se guarda en su carpeta de proyecto en uno o más archivos XSD.  \(Para cada espacio de nombres XML del esquema, se crea un archivo.\)  
  
#### Para crear un archivo de esquema XSD para un archivo XML mediante la inferencia del esquema en el Editor XML de Visual Studio  
  
1.  Modifique el archivo XML en el Diseñador XML de Visual Studio.  
  
2.  Cuando el cursor esté en alguna parte del archivo XML, aparece el menú **XML**.  Haga clic en la opción **Crear esquema** del menú **XML**.  Un archivo XSD se crea a partir del esquema XSD inferido del archivo XML.  
  
3.  Guarde el archivo de esquema XSD.  
  
    > [!NOTE]
    >  Los distintos esquemas XSD se podrían deducir de varios documentos XML que se piensa que tienen el mismo esquema.  Esto se puede producir cuando elementos y atributos concretos se encuentran en un archivo XML y no en otro, o cuando los elementos están incluidos en orden diferente, por ejemplo.  Debe revisar los esquemas XSD deducidos respecto a su integridad y exactitud al utilizar la inferencia del esquema XSD.  
  
#### Para incluir un archivo de esquema XSD  
  
-   De forma predeterminada, no puede ver archivos XSD en proyectos de Visual Basic.  Si el archivo XSD ya está incluido en las carpetas del proyecto, haga clic en el botón **Mostrar todos los archivos** del **Explorador de soluciones**.  Busque el archivo XSD en el **Explorador de soluciones**, haga clic con el botón secundario en el archivo y haga clic en **Incluir el archivo en el proyecto**.  
  
-   Si el archivo XSD aún no forma la parte del proyecto, en el **Explorador de soluciones**, haga clic con el botón secundario en la carpeta en la que desee almacenarlo, elija **Agregar**y, a continuación, haga clic en **Elemento existente**.  Busque el archivo XSD y, a continuación, haga clic en **Agregar**.  
  
#### Para importar un espacio de nombres XML en un archivo de código  
  
1.  Identifique el espacio de nombres de destino del esquema XSD.  
  
2.  Al principio del archivo de código, agregue una instrucción `Imports` para el espacio de nombres XML de destino, como se muestra en el ejemplo siguiente.  
  
     [!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-enable-xml-intell_1.vb)]  
  
     Para importar un espacio de nombres XML como el espacio de nombres predeterminado, es decir, el espacio de nombres que se aplica a los elementos y atributos XML que no tienen prefijo de espacio de nombres, agregue una instrucción `Imports` para el espacio de nombres XML predeterminado de destino.  No especifique ningún prefijo de espacio de nombres.  A continuación, se muestra un ejemplo de una instrucción `Imports`.  
  
     [!code-vb[VbXmlSamples#50](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-enable-xml-intell_2.vb)]  
  
#### Para importar un espacio de nombres XML para todos los archivos de un proyecto  
  
1.  Un espacio de nombres XML importado en un archivo de código sólo se aplica a ese archivo de código.  Para importar un espacio de nombres XML que se aplique a todos los archivos de código de un proyecto, abra el Diseñador de proyectos haciendo doble clic en **My Project** en el **Explorador de soluciones**.  
  
2.  En el cuadro **Espacios de nombres importados** de la ficha **Referencias**, escriba el espacio de nombres XML de destino con el formato de una declaración de espacio de nombres XML completa \(por ejemplo, `<xmlns: ns="http://sampleNamespace">`\).  Si el espacio de nombres XML de destino no especifica ningún prefijo de espacio de nombres, el espacio de nombres será el espacio de nombres XML predeterminado del proyecto.  
  
3.  Haga clic en **Agregar importación del usuario**.  
  
## Vea también  
 [Imports \(Instrucción, Espacio de nombres XML\)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [Página Referencias, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic)   
 [IntelliSense XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)