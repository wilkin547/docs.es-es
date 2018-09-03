---
title: El archivo especificado en Nombre de archivo no es un archivo XML válido
ms.date: 07/20/2015
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
ms.openlocfilehash: 3aecb0c2c87539717656a29f5b48f94fce3c8453
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43481881"
---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a>El archivo especificado en Nombre de archivo no es un archivo XML válido
El nombre de archivo proporcionado no es un archivo XML válido. Para especificar la estructura permitida y el contenido de un documento XML, puede usar una definición de tipo de documento (DTD), un esquema reducido de datos XML (XDR) de Microsoft o un esquema de lenguaje de definición de esquema XML (XSD). Los esquemas XSD son el método preferido para especificar gramáticas XML en [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].  
  
> [!NOTE]
>  En algunas versiones anteriores de Visual Studio, el **Diseñador XML** era el diseñador de los conjuntos de datos y el esquema XML. El **Diseñador XML** aún puede usarse para crear y editar archivos de esquema XML. Sin embargo, en [!INCLUDE[vs_current_long](~/includes/vs-current-long-md.md)], el diseñador para crear y editar conjuntos de datos es el **Diseñador de Dataset**. Para obtener más información, consulte [crear y editar conjuntos de datos con tipo](/visualstudio/data-tools/creating-and-editing-typed-datasets).  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Compruebe que está proporcionando el nombre de archivo correcto.  
  
-   Asegúrese de que el archivo especificado contiene XML válido. Para ello, cargue el archivo XML que desea comprobar en el **Diseñador XML**. En el menú **XML** , haga clic en **Validar datos XML**. Los errores se muestran en la ventana **Lista de tareas**.  
  
-   Si el archivo XML tiene un esquema XML asociado, compruebe que los elementos aparecen en la estructura definida y que el contenido de los elementos individuales se ajusta a los tipos de datos declarados especificados en el esquema.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml>  
 [Analizar rutas de acceso a archivos](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
