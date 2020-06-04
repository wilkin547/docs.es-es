---
title: GetType Operator
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 37644a9c37ffde084120c5f1e1ee8c87a04ffc3c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371160"
---
# <a name="gettype-operator-visual-basic"></a>GetType (Operador, Visual Basic)
Devuelve un <xref:System.Type> objeto para el tipo especificado. El <xref:System.Type> objeto proporciona información sobre el tipo, como sus propiedades, métodos y eventos.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---|---|  
|`typename`|Nombre del tipo del que se desea obtener información.|  
  
## <a name="remarks"></a>Observaciones  
 El `GetType` operador devuelve el <xref:System.Type> objeto para el especificado `typename` . Puede pasar el nombre de cualquier tipo definido en `typename` . Incluye lo siguiente:  
  
- Cualquier tipo de datos Visual Basic, como `Boolean` o `Date` .  
  
- Cualquier .NET Framework clase, estructura, módulo o interfaz, como <xref:System.ArgumentException?displayProperty=nameWithType> o <xref:System.Double?displayProperty=nameWithType> .  
  
- Cualquier clase, estructura, módulo o interfaz definida por la aplicación.  
  
- Cualquier matriz definida por la aplicación.  
  
- Cualquier delegado definido por la aplicación.  
  
- Cualquier enumeración definida por Visual Basic, la .NET Framework o la aplicación.  
  
 Si desea obtener el objeto de tipo de una variable de objeto, use el <xref:System.Type.GetType%2A?displayProperty=nameWithType> método.  
  
 El `GetType` operador puede ser útil en las siguientes circunstancias:  
  
- Debe tener acceso a los metadatos de un tipo en tiempo de ejecución. El <xref:System.Type> objeto proporciona metadatos, como los miembros de tipo e información de implementación. Necesita esto, por ejemplo, para reflejarse en un ensamblado. Para obtener más información, vea <xref:System.Reflection?displayProperty=nameWithType>.  
  
- Desea comparar dos referencias de objeto para ver si hacen referencia a instancias del mismo tipo. Si lo hacen, `GetType` devuelve referencias al mismo <xref:System.Type> objeto.  
  
## <a name="example"></a>Ejemplo  
 En los siguientes ejemplos se muestra el `GetType` operador en uso.  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a>Consulte también

- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Operadores y expresiones](../../programming-guide/language-features/operators-and-expressions/index.md)
