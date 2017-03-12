---
title: "Asistente XML a esquema (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.XmlToSchemaWizard"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "IntelliSense [Visual Basic], XML"
  - "XML [Visual Basic], IntelliSense"
  - "XML IntelliSense [Visual Basic]"
  - "esquemas XML, crear"
ms.assetid: 98c495ba-8f37-4517-a0db-aa738611ab76
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Asistente XML a esquema (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Utilice el Asistente de XML a esquema para crear un conjunto de esquemas XML que se infiere de uno o más documentos XML e incluirlo en el proyecto.  Puede utilizar cualquier combinación de documentos XML en forma de archivos de texto, XML de direcciones de Internet HTTP o XML que esté escrito o pegado en el Asistente de XML a esquema.  
  
 Los esquemas XML se utilizan a fin de proporcionar IntelliSense para las propiedades XML de Visual Basic.  Para obtener más información, vea [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) y [IntelliSense XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md).  
  
> [!NOTE]
>  Antes de ejecutar el Asistente de XML a esquema, se recomienda quitar cualquier archivo XSD existente del proyecto generado previamente por el asistente.  Si infiere un conjunto de esquemas XML que coincida con un conjunto de esquemas existente, se puede producir un conflicto y [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] no podrá proporcionar IntelliSense para las propiedades XML.  
  
 El Asistente de XML a esquema utiliza la clase <xref:System.Xml.Schema.XmlSchemaInference> a fin de crear el esquema para el XML proporcionado.  Como resultado, se pueden crear varios archivos de esquema para el conjunto de esquemas.  Para cada espacio de nombres XML en el XML proporcionado, se crea un archivo XSD \(Extensible Schema Definition\).  Para obtener más información, vea el método <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>.  
  
 Para tener acceso al Asistente de XML a esquema, haga clic en **Agregar nuevo elemento** en el menú **Proyecto** y agregue una plantilla **XML a esquema** del grupo de plantillas **Datos** o **Elementos comunes**.  Después de haber incluido todos los orígenes de documentos XML desde los que inferir el conjunto de esquemas XML, haga clic en **Aceptar** para crear el conjunto de esquemas inferido.  
  
 **Tipo de origen**  
 Esta columna muestra el tipo de origen del documento XML: **Archivo**, **Dirección URL** o **XML**.  
  
 **Ubicación de documentos XML**  
 Esta columna muestra la ruta de acceso del documento XML.  Para los documentos XML escritos o pegados, muestra el contenido del documento XML.  
  
 **Agregar desde archivo**  
 Haga clic en este botón para agregar archivos de documento XML mediante el Explorador del archivo.  
  
 **Agregar desde web**  
 Haga clic en este botón para proporcionar la dirección HTTP de un documento XML.  
  
 **Escribir o pegar XML**  
 Haga clic en este botón para escribir o pegar un documento XML en el cuadro de diálogo.  
  
## Vea también  
 <xref:System.Xml.Schema.XmlSchemaInference>   
 [IntelliSense XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)