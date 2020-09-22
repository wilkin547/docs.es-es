---
title: <param>
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 19300a928a59c7259f81b282bd28d9bdd447d76b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872622"
---
# <a name="param-visual-basic"></a>\<param> (Visual Basic)

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

 La etiqueta `<param>` debe usarse en el comentario de una declaración de método para describir uno de los parámetros del método.  
  
 El texto de la `<param>` etiqueta aparecerá en las siguientes ubicaciones:  
  
- Información de parámetros de IntelliSense. Para obtener más información, vea [Usar IntelliSense](/visualstudio/ide/using-intellisense).  
  
- Examinador de objetos. Para obtener más información, vea [ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).  
  
 Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se usa la `<param>` etiqueta para describir el `id` parámetro.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Consulte también

- [Etiquetas de comentario XML](index.md)
