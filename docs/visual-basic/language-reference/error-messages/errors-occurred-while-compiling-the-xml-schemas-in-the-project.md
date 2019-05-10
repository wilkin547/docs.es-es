---
title: Se produjeron errores al compilar los esquemas XML del proyecto
ms.date: 07/20/2015
f1_keywords:
- bc36810
- vbc36810
helpviewer_keywords:
- BC36810
ms.assetid: 9323b5d2-ba14-4e49-91f1-9ad647162144
ms.openlocfilehash: 7c05c712bcbb0a61bb3121bb71a7823a1c29afb5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625581"
---
# <a name="errors-occurred-while-compiling-the-xml-schemas-in-the-project"></a>Se produjeron errores al compilar los esquemas XML del proyecto
Se produjeron errores al compilar los esquemas XML en el proyecto. Por este motivo, IntelliSense XML no está disponible.  
  
 Hay un error en un esquema de definición de esquemas XML (XSD) incluido en el proyecto. Este error se produce cuando se agrega un archivo de esquema (.xsd) de XSD que entra en conflicto con el esquema XSD existente configurado para el proyecto.  
  
 **Identificador de error:** BC36810  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Haga doble clic en la advertencia en el **lista de errores** ventana. Visual Basic le llevará a la ubicación del archivo XSD que es el origen de la advertencia. Corrija el error en el esquema XSD.  
  
- Asegúrese de que todos los necesarios archivos XSD de esquema (.xsd) se incluyen en el proyecto. Que deba hacer clic **mostrar todos los archivos** en el **proyecto** menú para ver la XSD de archivos en **el Explorador de soluciones**. Haga clic en un archivo .xsd y, a continuación, haga clic en **incluir en el proyecto** para incluir el archivo en el proyecto.  
  
- Si usas el Asistente XML a esquema, este error puede producirse si deducir esquemas más de una vez desde el mismo origen. En este caso, puede quitar los archivos de esquema XSD existentes desde el proyecto, agregue un archivo XML nuevo a la plantilla de elemento de esquema y, a continuación, proporcionar el XML al Asistente para esquemas con todos los orígenes XML aplicable para el proyecto.  
  
- Si no se identifica ningún error en el esquema XSD, el compilador XML no puede tener suficiente información para proporcionar un mensaje de error detallado. Es posible que pueda obtener información más detallada del error si está seguro de que los espacios de nombres XML para los archivos .xsd incluyan en el proyecto coinciden con los espacios de nombres XML identificados en el esquema XML en Visual Studio.  
  
## <a name="see-also"></a>Vea también

- [Lista de errores (Ventana)](/visualstudio/ide/reference/error-list-window)
- [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
