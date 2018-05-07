---
title: Se produjeron errores al compilar los esquemas XML del proyecto
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 0cc565809792c619ca9903f9ef9b029b51a8aa17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a>Se produjeron errores al compilar los esquemas XML del proyecto
Se produjeron errores durante la compilación de los esquemas XML en el proyecto. Por este motivo, IntelliSense XML no está disponible.  
  
 Hay un error en un esquema de definición de esquemas XML (XSD) incluido en el proyecto. Este error se produce cuando se agrega un archivo de esquema (.xsd) de XSD que está en conflicto con el esquema XSD existente establecida para el proyecto.  
  
 **Id. de error:** BC36810  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Haga doble clic en la advertencia en el **lista de errores** ventana. Visual Basic le llevará a la ubicación del archivo XSD que es el origen de la advertencia. Corrija el error en el esquema XSD.  
  
-   Asegúrese de que todos los necesarios se incluyen archivos de esquema (.xsd) de XSD en el proyecto. Debe hacer clic en **mostrar todos los archivos** en el **proyecto** archivos de menú para ver su .xsd en **el Explorador de soluciones**. Haga clic en un archivo .xsd y, a continuación, haga clic en **incluir en el proyecto** para incluir el archivo en el proyecto.  
  
-   Si usas el Asistente de XML a esquema, este error puede producirse si deduce esquemas más de una vez desde el mismo origen. En este caso, puede quitar los archivos de esquema XSD existentes desde el proyecto, agregue un nuevo XML en la plantilla de elementos de esquema y, a continuación, escriba el XML en el Asistente para esquemas con todos los orígenes XML aplicables para el proyecto.  
  
-   Si no se identifica ningún error en el esquema XSD, el compilador XML no puede tener información suficiente para proporcionar un mensaje de error detallado. Es posible que pueda obtener información más detallada del error si está seguro de que los espacios de nombres XML para los archivos .xsd incluyan en el proyecto coinciden con los espacios de nombres XML identificados para el esquema XML en Visual Studio.  
  
## <a name="see-also"></a>Vea también  
 [Lista de errores (Ventana)](/visualstudio/ide/reference/error-list-window)  
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
