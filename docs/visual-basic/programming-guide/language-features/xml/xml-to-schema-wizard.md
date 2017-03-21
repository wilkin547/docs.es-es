---
title: Asistente XML a esquema (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vb.XmlToSchemaWizard
dev_langs:
- VB
helpviewer_keywords:
- XML IntelliSense [Visual Basic]
- XML [Visual Basic], IntelliSense
- IntelliSense [Visual Basic], XML
- XML schemas, creating
ms.assetid: 98c495ba-8f37-4517-a0db-aa738611ab76
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: d0c9c0247f3d9934ef973c7322cb098f9b445a5a
ms.lasthandoff: 03/13/2017

---
# <a name="xml-to-schema-wizard-visual-basic"></a>Asistente XML a esquema (Visual Basic)
Utilice el Asistente de XML a esquema para crear un conjunto de esquemas XML que se infiere de uno o más documentos XML e incluirlo en su proyecto. Puede utilizar cualquier combinación de documentos XML en forma de archivos de texto, XML de direcciones de HTTP Internet o XML que esté escrito o pegado en el Asistente de XML a esquema.  
  
 Esquemas XML se utilizan para proporcionar IntelliSense para propiedades XML en Visual Basic. Para obtener más información, consulte [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) y [IntelliSense XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md).  
  
> [!NOTE]
>  Antes de ejecutar al Asistente para esquemas XML, se recomienda que quite cualquier archivo XSD existente del proyecto generado previamente por el asistente. Si inferir un conjunto de esquemas XML que coincida con un conjunto de esquemas existente, se puede producir un conflicto y [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] no podrá proporcionar IntelliSense para propiedades XML.  
  
 El Asistente de XML a esquema utiliza la <xref:System.Xml.Schema.XmlSchemaInference>clase para crear el esquema para el XML proporcionado.</xref:System.Xml.Schema.XmlSchemaInference> Como resultado, pueden crearse varios archivos de esquema para el conjunto de esquemas. Para cada espacio de nombres XML en el XML proporcionado, se crea un archivo Extensible Schema Definition (XSD). Para obtener más información, consulte el <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>método.</xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>  
  
 Para tener acceso el Asistente de XML a esquema, haga clic en **Agregar nuevo elemento** en el **proyecto** menú y agregue un **XML a esquema** plantilla desde el **datos** o **elementos comunes** grupo de plantillas. Una vez que ha incluido todos los orígenes de documentos XML para inferir el conjunto de esquemas XML desde, haga clic en **Aceptar** para crear el esquema deducido conjunto.  
  
 **Tipo de origen**  
 Esta columna muestra el tipo de origen del documento XML: **archivo**, **URL**, o **XML**.  
  
 **Ubicación del documento XML**  
 Esta columna muestra la ruta de acceso del documento XML. Para documentos XML escritos o pegados, muestra el contenido del documento XML.  
  
 **Agregar desde archivo**  
 Haga clic en este botón para agregar archivos de documento XML mediante el Explorador de archivos.  
  
 **Agregar desde el Web**  
 Haga clic en este botón para proporcionar la dirección HTTP de un documento XML.  
  
 **Escribir o pegar XML**  
 Haga clic en este botón para escribir o pegar un documento XML en el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Schema.XmlSchemaInference></xref:System.Xml.Schema.XmlSchemaInference>   
 [XML IntelliSense en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)
