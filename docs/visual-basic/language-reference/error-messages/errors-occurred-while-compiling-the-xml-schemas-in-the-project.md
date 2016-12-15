---
title: "Se produjeron errores al compilar los esquemas XML del proyecto | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc36810"
  - "vbc36810"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36810"
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Se produjeron errores al compilar los esquemas XML del proyecto
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Se produjeron errores al compilar los esquemas XML del proyecto.Por ello, no está disponible la característica IntelliSense XML.  
  
 Hay un error en el esquema de definición de esquema XML \(XSD\) incluido en el proyecto.  Este error se produce al agregar un archivo de esquema XSD \(.xsd\) que entra en conflicto con el conjunto de esquemas XSD existente para el proyecto.  
  
 **Id. de error:** BC36810  
  
### Para corregir este error  
  
-   En la ventana **Lista de errores**, haga doble clic en la advertencia.  Visual Basic lo llevará a la ubicación del archivo XSD que es el origen de la advertencia.  Corrija el error en el esquema XSD.  
  
-   Asegúrese de que todos los archivos de esquema XSD \(.xsd\) necesarios están incluidos en el proyecto.  Quizás necesite hacer clic en **Mostrar todos los archivos**, en el menú **Proyecto**, para ver sus archivos .xsd en el **Explorador de soluciones**.  Haga clic con el botón secundario en un archivo .xsd y, a continuación, haga clic en **Incluir en el proyecto** para incluir el archivo en su proyecto.  
  
-   Si está utilizando el Asistente de XML a esquema, este error se puede producir si deduce esquemas más de una vez desde el mismo origen.  En este caso, puede quitar los archivos de esquema XSD existentes del proyecto, agregar una nueva plantilla de elementos de XML a esquema y, a continuación, proporcionar al Asistente de XML a esquema todos los orígenes XML aplicables para el proyecto.  
  
-   Si no se identifica ningún error en el esquema XSD, puede que el compilador XML no tenga suficiente información para proporcionar un mensaje de error detallado.  Puede que obtenga más información detallada sobre errores si se asegura de que los espacios de nombres XML para los archivos .xsd incluidos en el proyecto coinciden con los espacios de nombres XML identificados para el esquema XML establecido en Visual Studio.  
  
## Vea también  
 [Lista de errores \(Ventana\)](/visual-studio/ide/reference/error-list-window)   
 [IntelliSense XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)