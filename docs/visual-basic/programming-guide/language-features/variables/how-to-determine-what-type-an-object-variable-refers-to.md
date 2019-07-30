---
title: Procedimiento Determinar el tipo al que hace referencia una variable de objeto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 935623dd4b6edca188f932aca0e560130199e8f6
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626574"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a>Procedimiento Determinar el tipo al que hace referencia una variable de objeto (Visual Basic)

Una variable de objeto contiene un puntero a los datos que se almacenan en otro lugar. El tipo de datos que pueden cambiar durante el tiempo de ejecución. En cualquier momento, puede usar el <xref:System.Type.GetTypeCode%2A> método para determinar el tipo en tiempo de ejecución actual o el [operador typeof](../../../../visual-basic/language-reference/operators/typeof-operator.md) para averiguar si el tipo en tiempo de ejecución actual es compatible con un tipo especificado.

### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a>Para determinar el tipo exacto al que una variable de objeto hace referencia actualmente

1. En la variable de objeto, llame <xref:System.Object.GetType%2A> al método para recuperar <xref:System.Type?displayProperty=nameWithType> un objeto.

    ```vb
    Dim myObject As Object
    myObject.GetType()
    ```

2. En la <xref:System.Type?displayProperty=nameWithType> clase, llame al método <xref:System.Type.GetTypeCode%2A> compartido para recuperar el <xref:System.TypeCode> valor de enumeración para el tipo del objeto.

    ```vb
    Dim myObject As Object
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())
    MsgBox("myObject currently has type code " & CStr(datTyp))
    ```

    Puede probar el valor <xref:System.TypeCode> de la enumeración con cualquier miembro de la enumeración que `Double`sea de interés, como.

### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a>Para determinar si el tipo de una variable de objeto es compatible con un tipo especificado

- Use el `TypeOf` operador junto con el [operador is](../../../../visual-basic/language-reference/operators/is-operator.md) para probar `TypeOf`el objeto con... `Is` expresión.

    ```vb
    If TypeOf objA Is System.Windows.Forms.Control Then
        MsgBox("objA is compatible with the Control class")
    End If
    ```

    `TypeOf`... la expresión `True` devuelve si el tipo en tiempo de ejecución del objeto es compatible con el tipo especificado. `Is`

    El criterio de compatibilidad depende de si el tipo especificado es una clase, una estructura o una interfaz. En general, los tipos son compatibles si el objeto es del mismo tipo que, hereda de o implementa el tipo especificado. Para obtener más información, vea [operador typeof](../../../../visual-basic/language-reference/operators/typeof-operator.md).

## <a name="compiling-the-code"></a>Compilar el código

Tenga en cuenta que el tipo especificado no puede ser una variable o una expresión. Debe ser el nombre de un tipo definido, como una clase, una estructura o una interfaz. Esto incluye tipos intrínsecos como `Integer` y `String`.

## <a name="see-also"></a>Vea también

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Valores de las variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Tipo de objeto de datos](../../../../visual-basic/language-reference/data-types/object-data-type.md)
