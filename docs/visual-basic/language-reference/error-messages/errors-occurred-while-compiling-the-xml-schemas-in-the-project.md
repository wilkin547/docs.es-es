---
title: Se produjeron errores al compilar los esquemas XML en el proyecto | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36810
- vbc36810
dev_langs:
- VB
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
caps.latest.revision: 11
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
ms.openlocfilehash: cf04e85da98db53d1c78269169571936f708cd21
ms.lasthandoff: 03/13/2017

---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a>Se produjeron errores al compilar los esquemas XML del proyecto
Se produjeron errores al compilar los esquemas XML en el proyecto. Por este motivo, IntelliSense XML no está disponible.  
  
 Hay un error en un esquema de definición de esquemas XML (XSD) incluido en el proyecto. Este error se produce cuando se agrega un archivo de esquema (.xsd) de XSD que entra en conflicto con el esquema XSD existente establecido para el proyecto.  
  
 **Id. de error:** BC36810  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Haga doble clic en la advertencia en el **lista de errores** ventana. Visual Basic le llevará a la ubicación del archivo XSD que es el origen de la advertencia. Corrija el error en el esquema XSD.  
  
-   Asegúrese de que todos los necesarios se incluyen los archivos de esquema (.xsd) de XSD en el proyecto. Puede que necesite hacer clic en **mostrar todos los archivos** en el **proyecto** archivos de menú para ver su .xsd en **el Explorador de soluciones**. Haga clic en un archivo .xsd y, a continuación, haga clic en **incluir en el proyecto** para incluir el archivo en el proyecto.  
  
-   Si utiliza el Asistente de XML a esquema, este error puede producirse si deduce esquemas más de una vez desde el mismo origen. En este caso, puede quitar los archivos de esquema XSD existentes desde el proyecto, agregar un archivo XML nuevo a la plantilla de elemento de esquema y, a continuación, proporcionar el XML a esquema asistente con todos los orígenes XML aplicables para el proyecto.  
  
-   Si no se identifica ningún error en el esquema XSD, el compilador XML no tenga suficiente información para proporcionar un mensaje de error detallado. Es posible que pueda obtener información más detallada del error, si está seguro de que los espacios de nombres XML para los archivos .xsd incluyan en el proyecto coinciden con los espacios de nombres XML identificados para el esquema XML establecido en Visual Studio.  
  
## <a name="see-also"></a>Vea también  
 [Ventana Lista de errores](https://docs.microsoft.com/visualstudio/ide/reference/error-list-window)   
 [XML IntelliSense en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
