---
title: <list> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- listheader XML tag
- <item> XML tag
- <list> XML tag
- <listheader> XML tag
- term XML tag
- list XML tag
- <description> XML tag
- description XML tag
- item XML tag
- <term> XML tag
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
ms.openlocfilehash: 5d4295d485611e75e8b6c8d8f95e079654f0cfa3
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524752"
---
# <a name="list-visual-basic"></a>\<list > (Visual Basic)
Define una lista o una tabla.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<list type="type">  
   <listheader>  
      <term>term</term>  
      <description>description</description>  
   </listheader>  
   <item>  
      <term>term</term>  
      <description>description</description>  
   </item>  
</list>  
```  
  
## <a name="parameters"></a>Parámetros  
 `type`  
 El tipo de la lista. Debe ser una "viñeta" para una lista con viñetas, "número" para una lista numerada o "tabla" para una tabla de dos columnas.  
  
 `term`  
 Solo se usa cuando `type` es "Table". Un término para definir, que se define en la etiqueta de descripción.  
  
 `description`  
 Cuando `type` es "Bullet" o "Number", `description` es un elemento de la lista cuando `type` es "Table" `description` es la definición de `term`.  
  
## <a name="remarks"></a>Comentarios  
 El bloque `<listheader>` define el encabezado de una tabla o de una lista de definiciones. Al definir una tabla, solo tiene que proporcionar una entrada para `term` en el encabezado.  
  
 Cada elemento de la lista se especifica con un bloque `<item>`. Al crear una lista de definiciones, debe especificar `term` y `description`. Sin embargo, para una tabla, una lista con viñetas o una lista numerada, solo tiene que proporcionar una entrada para `description`.  
  
 Una lista o una tabla puede tener tantos bloques de `<item>` como sea necesario.  
  
 Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa la etiqueta `<list>` para definir una lista con viñetas en la sección Comentarios.  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>Vea también

- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
