---
title: El tipo de la variable '<variablename>' no se inferirá porque está enlazado a un campo en un ámbito de inclusión
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: 98aeb5699fdd5e5e538a205acd37436019c3fc03
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363051"
---
# <a name="the-type-for-variable-variablename-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a>El tipo de la variable '\<variablename>' no se inferirá porque está enlazado a un campo en un ámbito de inclusión

El tipo de la variable ' \<variablename> ' no se inferirá porque está enlazado a un campo en un ámbito de inclusión. Cambie el nombre de ' \<variablename> ' o use el nombre completo (por ejemplo, ' me. variablename ' o ' MyBase. variablename ').

Una variable de control de bucle en su código tiene el mismo nombre que un campo de la clase u otro ámbito de inclusión. Dado que la variable de control se utiliza sin una cláusula `As`, se enlaza al campo en el ámbito de inclusión y el compilador no crea una nueva variable para ella ni infiere su tipo.

En el ejemplo siguiente, `Index`, es decir, la variable de control en la instrucción `For`, se enlaza al campo `Index` de la clase `Customer`. El compilador no crea una nueva variable para la variable de control `Index` ni infiere su tipo.

```vb
Class Customer

    ' The class has a field named Index.
    Private Index As Integer

    Sub Main()

    ' The following line will raise this warning.
        For Index = 1 To 10
            ' ...
        Next

    End Sub
End Class
```

De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

**Identificador de error:** BC42110

### <a name="to-address-this-warning"></a>Para resolver esta advertencia

- Convierta la variable de control de bucle en local cambiando su nombre por un identificador que tampoco sea el nombre de un campo de la clase.

  ```vb
  For I = 1 To 10
  ```

- Asegúrese de que la variable de control de bucle se enlaza al campo de clase agregando el prefijo `Me.` al nombre de variable.

  ```vb
  For Me.Index = 1 To 10
  ```

- En lugar de basarse en la inferencia de tipo local, use una cláusula `As` para especificar un tipo para la variable de control de bucle.

  ```vb
  For Index As Integer = 1 To 10
  ```

## <a name="example"></a>Ejemplo
 El código siguiente muestra el ejemplo anterior con la primera corrección en contexto.

```vb
Class Customer

    ' The class has a field named Index.
    Private Index As Integer

    Sub Main()

        For I = 1 To 10
            ' ...
        Next

    End Sub
End Class
```

## <a name="see-also"></a>Consulte también

- [Option Infer (instrucción)](../statements/option-infer-statement.md)
- [Instrucción For Each...Next](../statements/for-each-next-statement.md)
- [Instrucción For...Next](../statements/for-next-statement.md)
- [Procedimiento para hacer referencia a la instancia actual de un objeto](../../programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [Inferencia de tipo de variable local](../../programming-guide/language-features/variables/local-type-inference.md)
- [Me, My, MyBase y MyClass](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
