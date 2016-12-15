---
title: "Hay un acceso de propiedad Default ambiguo entre los miembros &lt;nombreDePropiedadPredeterminado&gt; heredados de la interfaz &lt;nombreDeInterfaz1&gt; y &lt;nombreDePropiedadPredeterminado&gt; de la interfaz &lt;nombreDeInterfaz2&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30686"
  - "bc30686"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30686"
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Hay un acceso de propiedad Default ambiguo entre los miembros &lt;nombreDePropiedadPredeterminado&gt; heredados de la interfaz &lt;nombreDeInterfaz1&gt; y &lt;nombreDePropiedadPredeterminado&gt; de la interfaz &lt;nombreDeInterfaz2&gt;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una interfaz hereda de dos interfaces, cada una de las cuales declara una propiedad predeterminada con el mismo nombre.  El compilador no puede resolver un acceso a esta propiedad predeterminada sin calificación.  Esto se ilustra en el siguiente ejemplo:  
  
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
  
 Cuando especifica `testObj(1)`, el compilador intenta resolverlo con la propiedad predeterminada.  Sin embargo, hay dos propiedades predeterminadas posibles debido a las interfaces heredadas, por lo que el compilador señala este error.  
  
 **Identificador de error:** BC30686  
  
### Para corregir este error  
  
-   Evite heredar miembros con el mismo nombre.  En el ejemplo anterior, si `testObj` no necesita ninguno miembro, por ejemplo, `Iface2`, declárelo del modo siguiente:  
  
    ```  
    Dim testObj As Iface1  
    ```  
  
     O bien  
  
-   Implemente la interfaz que hereda en una clase.  A continuación, puede implementar cada una de las propiedades heredadas con nombres diferentes.  Sin embargo, sólo una de ellas puede ser la propiedad predeterminada de la clase de implementación.  Esto se ilustra en el siguiente ejemplo:  
  
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
  
## Vea también  
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)