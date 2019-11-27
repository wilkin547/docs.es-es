---
title: GetType Operator
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 4e59bcfaa24c9545ed75c6b5c1d29cad398ac2de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349549"
---
# <a name="gettype-operator-visual-basic"></a>GetType (Operador, Visual Basic)
Devuelve un objeto <xref:System.Type> para el tipo especificado. El objeto <xref:System.Type> proporciona información sobre el tipo, como sus propiedades, métodos y eventos.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---|---|  
|`typename`|Nombre del tipo del que se desea obtener información.|  
  
## <a name="remarks"></a>Comentarios  
 El operador `GetType` devuelve el objeto <xref:System.Type> para el `typename`especificado. Puede pasar el nombre de cualquier tipo definido en `typename`. Entre estas estructuras se incluyen las siguientes:  
  
- Cualquier tipo de datos Visual Basic, como `Boolean` o `Date`.  
  
- Cualquier .NET Framework clase, estructura, módulo o interfaz, como <xref:System.ArgumentException?displayProperty=nameWithType> o <xref:System.Double?displayProperty=nameWithType>.  
  
- Cualquier clase, estructura, módulo o interfaz definida por la aplicación.  
  
- Cualquier matriz definida por la aplicación.  
  
- Cualquier delegado definido por la aplicación.  
  
- Cualquier enumeración definida por Visual Basic, la .NET Framework o la aplicación.  
  
 Si desea obtener el objeto de tipo de una variable de objeto, use el método <xref:System.Type.GetType%2A?displayProperty=nameWithType>.  
  
 El operador `GetType` puede ser útil en las siguientes circunstancias:  
  
- Debe tener acceso a los metadatos de un tipo en tiempo de ejecución. El objeto <xref:System.Type> proporciona metadatos, como los miembros de tipo e información de implementación. Necesita esto, por ejemplo, para reflejarse en un ensamblado. Para obtener más información, consulta <xref:System.Reflection?displayProperty=nameWithType>.  
  
- Desea comparar dos referencias de objeto para ver si hacen referencia a instancias del mismo tipo. Si lo hacen, `GetType` devuelve referencias al mismo objeto <xref:System.Type>.  
  
## <a name="example"></a>Ejemplo  
 En los siguientes ejemplos se muestra el operador de `GetType` en uso.  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a>Vea también

- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
