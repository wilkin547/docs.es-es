---
title: GetType (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 34ab192814583db5cdc0d0183c73cc22b8633e9c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663614"
---
# <a name="gettype-operator-visual-basic"></a>GetType (Operador, Visual Basic)
Devuelve un <xref:System.Type> objeto para el tipo especificado. La <xref:System.Type> objeto proporciona información sobre el tipo como sus propiedades, métodos y eventos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
GetType(typename)  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---|---|  
|`typename`|El nombre del tipo para el que se desea obtener información.|  
  
## <a name="remarks"></a>Comentarios  
 El `GetType` operador devuelve el <xref:System.Type> objeto para el elemento especificado `typename`. Puede pasar el nombre de cualquier tipo definido en `typename`. Entre estas estructuras se incluyen las siguientes:  
  
- Escriba los datos de Visual Basic, como `Boolean` o `Date`.  
  
- Cualquier clase, estructura, módulo o interfaz, .NET Framework, como <xref:System.ArgumentException?displayProperty=nameWithType> o <xref:System.Double?displayProperty=nameWithType>.  
  
- Cualquier clase, estructura, módulo o interfaz definida por la aplicación.  
  
- Cualquier matriz definida por la aplicación.  
  
- Cualquier delegado definido por la aplicación.  
  
- Cualquiera de las enumeraciones definida por la aplicación, .NET Framework o Visual Basic.  
  
 Si desea obtener el objeto de tipo de una variable de objeto, utilice el <xref:System.Type.GetType%2A?displayProperty=nameWithType> método.  
  
 El `GetType` operador puede ser útil en las siguientes circunstancias:  
  
- Debe tener acceso a los metadatos para un tipo en tiempo de ejecución. La <xref:System.Type> objeto proporciona los metadatos como miembros de tipo y la información de implementación. Necesita esto, por ejemplo, para reflejar a través de un ensamblado. Para obtener más información, consulta <xref:System.Reflection?displayProperty=nameWithType>.  
  
- Desea comparar dos referencias de objeto para ver si hacen referencia a las instancias del mismo tipo. Si lo hacen, `GetType` devuelve referencias al mismo <xref:System.Type> objeto.  
  
## <a name="example"></a>Ejemplo  
 Los ejemplos siguientes muestran el `GetType` operador en uso.  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a>Vea también

- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
