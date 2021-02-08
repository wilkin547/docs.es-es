---
description: "Más información sobre: BC30686: el acceso a la propiedad predeterminada es ambiguo entre los miembros heredados de la interfaz ' <defaultpropertyname> ' de la interfaz ' <interfacename1> ' y ' <defaultpropertyname> ' de la interfaz '<interfacename2>"
title: Hay un acceso de propiedad Default ambiguo entre los miembros <defaultpropertyname> heredados de la interfaz <interfacename1> y <defaultpropertyname> de la interfaz <interfacename2>
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: 5ae5e5b2dc7a61540e26d125e960d4755141d975
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796657"
---
# <a name="bc30686-default-property-access-is-ambiguous-between-the-inherited-interface-members-defaultpropertyname-of-interface-interfacename1-and-defaultpropertyname-of-interface-interfacename2"></a>BC30686: el acceso a la propiedad predeterminada es ambiguo entre los miembros heredados de la interfaz ' ' \<defaultpropertyname> de la interfaz ' \<interfacename1> ' y ' \<defaultpropertyname> ' de la interfaz ' \<interfacename2> '

Una interfaz hereda de dos interfaces, cada una de las cuales declara una propiedad predeterminada con el mismo nombre. El compilador no puede resolver un acceso a esta propiedad predeterminada sin calificación. Esto se ilustra en el siguiente ejemplo:

```vb
Public Interface Iface1
    Default Property prop(ByVal arg As Integer) As Integer
End Interface
Public Interface Iface2
    Default Property prop(ByVal arg As Integer) As Integer
End Interface
Public Interface Iface3
    Inherits Iface1, Iface2
End Interface
Public Class testClass
    Public Sub accessDefaultProperty()
        Dim testObj As Iface3
        Dim testInt As Integer = testObj(1)
    End Sub
End Class
```

Cuando se especifica `testObj(1)` , el compilador intenta resolverlo en la propiedad predeterminada. Sin embargo, hay dos propiedades predeterminadas posibles debido a las interfaces heredadas, por lo que el compilador señala este error.

**Identificador de error:** BC30686

## <a name="to-correct-this-error"></a>Para corregir este error

- Evite la herencia de miembros con el mismo nombre. En el ejemplo anterior, si no `testObj` necesita ninguno de los miembros de, por ejemplo, `Iface2` , declárelo como se indica a continuación:

  ```vb
  Dim testObj As Iface1
  ```

  O bien

- Implemente la interfaz heredada en una clase. A continuación, puede implementar cada una de las propiedades heredadas con nombres diferentes. Sin embargo, solo uno de ellos puede ser la propiedad predeterminada de la clase de implementación. Esto se ilustra en el siguiente ejemplo:

  ```vb
  Public Class useIface3
      Implements Iface3
      Default Public Property prop1(ByVal arg As Integer) As Integer Implements Iface1.prop
          ' Insert code to define Get and Set procedures for prop1.
      End Property
      Public Property prop2(ByVal arg As Integer) As Integer Implements Iface2.prop
          ' Insert code to define Get and Set procedures for prop2.
      End Property
  End Class
  ```

## <a name="see-also"></a>Vea también

- [Interfaces](../../programming-guide/language-features/interfaces/index.md)
