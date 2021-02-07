---
description: 'Más información acerca de: <param> (Visual Basic)'
title: <param>
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 94fe5e11d5846f7fa00eb73c1c4363990ae23b2f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700297"
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
  
## <a name="see-also"></a>Vea también

- [Etiquetas de comentario XML](index.md)
