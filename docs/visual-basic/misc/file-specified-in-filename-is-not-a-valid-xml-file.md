---
title: "Archivo especificado en el nombre de archivo no es un archivo XML válido | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2fa595ab411fdd300327db9e1fcca1e3156c7eed
ms.lasthandoff: 03/13/2017

---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a>El archivo especificado en Nombre de archivo no es un archivo XML válido
El nombre de archivo proporcionado no es un archivo XML válido. Para especificar la estructura permitida y el contenido de un documento XML, puede usar una definición de tipo de documento (DTD), un esquema reducido de datos XML (XDR) de Microsoft o un esquema de lenguaje de definición de esquema XML (XSD). Los esquemas XSD son la manera preferida de especificar las gramáticas XML en el [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)].  
  
> [!NOTE]
>  En algunas versiones anteriores de Visual Studio, el **Diseñador XML** era el diseñador de los conjuntos de datos y el esquema XML. El **Diseñador XML** aún puede usarse para crear y editar archivos de esquema XML. Sin embargo, en [!INCLUDE[vs_current_long](../../csharp/misc/includes/vs_current_long_md.md)], el diseñador para crear y editar los conjuntos de datos es el **Diseñador de Dataset**. Para obtener más información, consulte [crear y editar conjuntos de datos con tipo](https://docs.microsoft.com/visualstudio/data-tools/creating-and-editing-typed-datasets).  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Compruebe que está proporcionando el nombre de archivo correcto.  
  
-   Asegúrese de que el archivo especificado contiene XML válido. Para ello, cargue el archivo XML que desea comprobar en el **Diseñador XML**. En el menú **XML** , haga clic en **Validar datos XML**. Los errores se muestran en la ventana **Lista de tareas**.  
  
-   Si el archivo XML tiene un esquema XML asociado, compruebe que los elementos aparecen en la estructura definida y que el contenido de los elementos individuales se ajusta a los tipos de datos declarados especificados en el esquema.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml></xref:System.Xml>   
 [Analizar rutas de acceso a archivos](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
