---
title: Acceso a la propiedad predeterminada es ambiguo entre los miembros heredados de la interfaz &#39; &lt;defaultpropertyname&gt;&#39; de la interfaz &#39;&lt; interfacename1&gt;&#39; y &#39;&lt; defaultpropertyname&gt;&#39; de la interfaz &#39;&lt; interfacename2&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 23d613668ee2d92484117759dd614ed2cad4bcb2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-39ltdefaultpropertynamegt39-of-interface-39ltinterfacename1gt39-and-39ltdefaultpropertynamegt39-of-interface-39ltinterfacename2gt39"></a>Acceso a la propiedad predeterminada es ambiguo entre los miembros heredados de la interfaz &#39; &lt;defaultpropertyname&gt;&#39; de la interfaz &#39;&lt; interfacename1&gt;&#39; y &#39;&lt; defaultpropertyname&gt;&#39; de la interfaz &#39;&lt; interfacename2&gt;&#39;
Una interfaz hereda de dos interfaces, cada uno de los cuales declara una propiedad predeterminada con el mismo nombre. El compilador no puede resolver un acceso a esta propiedad predeterminada sin calificación. Esto se ilustra en el siguiente ejemplo:  
  
```  
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
  
 Cuando se especifica `testObj(1)`, el compilador intenta resolver en la propiedad predeterminada. Sin embargo, hay dos propiedades predeterminadas posibles debido a las interfaces heredadas, por lo que el compilador señala este error.  
  
 **Id. de error:** BC30686  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Evite heredar a miembros con el mismo nombre. En el ejemplo anterior, si `testObj` no necesita ninguno de los miembros de, por ejemplo, `Iface2`, declárelo como sigue:  
  
    ```  
    Dim testObj As Iface1  
    ```  
  
     O bien  
  
-   Implemente la interfaz que hereda de una clase. A continuación, puede implementar cada una de las propiedades heredadas con nombres diferentes. Sin embargo, sólo uno de ellos puede ser la propiedad predeterminada de la clase de implementación. Esto se ilustra en el siguiente ejemplo:  
  
    ```  
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
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
