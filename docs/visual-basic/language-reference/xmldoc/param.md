---
title: <param> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 4bcfe96361de9e196cb684ac4ba734f82442e25c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825565"
---
# <a name="param-visual-basic"></a>\<param > (Visual Basic)
Define un nombre de parámetro y una descripción.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a>Parámetros  
 `name`  
 Nombre de un parámetro de método. Ponga el nombre entre comillas dobles (" ").  
  
 `description`  
 Descripción del parámetro.  
  
## <a name="remarks"></a>Comentarios  
 El `<param>` etiqueta debe usarse en el comentario de una declaración de método para describir uno de los parámetros del método.  
  
 El texto para el `<param>` etiqueta aparecerá en las siguientes ubicaciones:  
  
-   Información de parámetros de IntelliSense. Para obtener más información, vea [Usar IntelliSense](/visualstudio/ide/using-intellisense).  
  
-   Examinador de objetos. Para obtener más información, vea [Ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `<param>` etiquetas para describir el `id` parámetro.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vea también

- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
