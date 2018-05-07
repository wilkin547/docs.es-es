---
title: GetType (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 581f576222eb149aede841a5da7a0e5f38c77b58
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="gettype-operator-visual-basic"></a>GetType (Operador, Visual Basic)
Devuelve un <xref:System.Type> objeto para el tipo especificado. La <xref:System.Type> objeto proporciona información sobre el tipo como sus propiedades, métodos y eventos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
GetType(typename)  
```  
  
#### <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---|---|  
|`typename`|El nombre del tipo para el que se desea obtener información.|  
  
## <a name="remarks"></a>Comentarios  
 El `GetType` operador devuelve el <xref:System.Type> objeto para el elemento especificado `typename`. Puede pasar el nombre de cualquier tipo definido en `typename`. Entre estas estructuras se incluyen las siguientes:  
  
-   Tipo de los datos de Visual Basic, como `Boolean` o `Date`.  
  
-   Cualquier clase, estructura, módulo o interfaz, .NET Framework como <xref:System.ArgumentException?displayProperty=nameWithType> o <xref:System.Double?displayProperty=nameWithType>.  
  
-   Cualquier clase, estructura, módulo o interfaz definida por la aplicación.  
  
-   Cualquier matriz definida por la aplicación.  
  
-   Cualquier delegado definido por la aplicación.  
  
-   Cualquiera de las enumeraciones definida por Visual Basic, .NET Framework o la aplicación.  
  
 Si desea obtener el objeto de tipo de una variable de objeto, utilice el <xref:System.Type.GetType%2A?displayProperty=nameWithType> método.  
  
 La `GetType` puede ser útil en las siguientes circunstancias:  
  
-   Debe tener acceso a los metadatos para un tipo en tiempo de ejecución. La <xref:System.Type> objeto que proporciona metadatos como miembros de tipo e información de implementación. Lo necesita, por ejemplo, para reflejar en un ensamblado. Para obtener más información, consulta <xref:System.Reflection?displayProperty=nameWithType>.  
  
-   Desea comparar dos referencias de objeto para ver si hacen referencia a instancias del mismo tipo. Si es así, `GetType` devuelve referencias a los mismos <xref:System.Type> objeto.  
  
## <a name="example"></a>Ejemplo  
 Los ejemplos siguientes muestran el `GetType` operador en uso.  
  
 [!code-vb[VbVbalrOperators#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/gettype-operator_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
