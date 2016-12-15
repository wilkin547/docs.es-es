---
title: "C&#243;mo: Implementar eventos de interfaz (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "eventos [C#], en interfaces"
  - "interfaces [C#], implementación de eventos en clases"
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Implementar eventos de interfaz (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una [interfaz](../../../csharp/language-reference/keywords/interface.md) puede declarar un [evento](../../../csharp/language-reference/keywords/event.md).  El ejemplo siguiente muestra cómo implementar eventos de interfaz en una clase.  Básicamente, las reglas son las mismas que cuando se implementa cualquier método de interfaz o propiedad.  
  
### Para implementar eventos de interfaz en una clase  
  
-   Declare el evento en la clase y, a continuación, invóquelo en las áreas adecuadas.  
  
    ```  
    namespace ImplementInterfaceEvents  
    {  
        public interface IDrawingObject  
        {  
            event EventHandler ShapeChanged;  
        }  
        public class MyEventArgs : EventArgs   
        {  
            // class members  
        }  
        public class Shape : IDrawingObject  
        {  
            public event EventHandler ShapeChanged;  
            void ChangeShape()  
            {  
                // Do something here before the event…  
  
                OnShapeChanged(new MyEventArgs(/*arguments*/));  
  
                // or do something here after the event.   
            }  
            protected virtual void OnShapeChanged(MyEventArgs e)  
            {  
                if(ShapeChanged != null)  
                {  
                   ShapeChanged(this, e);  
                }  
            }  
        }  
  
    }  
    ```  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo controlar la situación menos común en la que la clase se hereda de dos o más interfaces y cada interfaz tiene un evento con el mismo nombre.  En esta situación, debe proporcionar una implementación de interfaz explícita para al menos uno de los eventos.  Cuando escriba una implementación de interfaz explícita para un evento, también debe incluir los descriptores de acceso a eventos `add` y `remove`.  Normalmente, estos descriptores los proporciona el compilador, pero en este caso no es así.  
  
 Al proporcionar sus propios descriptores de acceso, puede especificar si los dos eventos se representan mediante el mismo evento en la clase o mediante eventos diferentes.  Por ejemplo, si los eventos deben provocarse en momentos diferentes según las especificaciones de la interfaz, luego puede asociar cada evento a una implementación distinta en la clase.  En el ejemplo siguiente, los suscriptores determinan qué evento `OnDraw` se recibirá convirtiendo la referencia de la forma en `IShape` o `IDrawingObject`.  
  
 [!code-cs[csProgGuideEvents#10](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-implement-interface-events_1.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Eventos](../../../csharp/programming-guide/events/index.md)   
 [Delegados](../../../csharp/programming-guide/delegates/index.md)   
 [Implementación explícita de interfaz](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)   
 [Cómo: Producir eventos de una clase base en clases derivadas](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)