---
title: "C&#243;mo: Publicar eventos que cumplan las directrices de .NET Framework (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "eventos [C#], instrucciones de implementación"
ms.assetid: 9310ae16-8627-44a2-b08c-05e5976202b1
caps.latest.revision: 31
caps.handback.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Publicar eventos que cumplan las directrices de .NET Framework (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En el procedimiento siguiente se muestra cómo puede agregar eventos que se ajusten al modelo estándar de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] en sus propias clases y structs.  Todos los eventos de la biblioteca de clases [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] se basan en el delegado <xref:System.EventHandler>, que se define del modo siguiente:  
  
```  
public delegate void EventHandler(object sender, EventArgs e);  
```  
  
> [!NOTE]
>  [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)] incluye una versión genérica de este delegado, <xref:System.EventHandler%601>.  Los ejemplos siguientes muestran cómo utilizar ambas versiones.  
  
 Aunque los eventos de las clases que defina se pueden basar en cualquier tipo de delegado válido, incluidos los delegados que devuelven un valor, normalmente es aconsejable que los eventos se basen en el modelo de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] a través de <xref:System.EventHandler>, como se muestra en el ejemplo siguiente.  
  
### Para publicar eventos basados en el modelo EventHandler  
  
1.  \(Omita este paso y vaya directamente al paso 3a si no tiene que enviar datos personalizados con el evento\). Declare la clase de sus datos personalizados en un ámbito que sea visible para las clases del publicador y del suscriptor.  A continuación, agregue los miembros necesarios para que contengan los datos de evento personalizados.  En este ejemplo, se devuelve una cadena simple.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
2.  \(Omita este paso si utiliza la versión genérica de <xref:System.EventHandler%601>\). Declare un delegado en la clase de publicación.  Asígnele un nombre que acabe en *EventHandler*.  El segundo parámetro especifica el tipo EventArgs personalizado.  
  
    ```  
    public delegate void CustomEventHandler(object sender, CustomEventArgs a);  
    ```  
  
3.  Declare el evento en la clase de publicación mediante alguno de los procedimientos siguientes.  
  
    1.  Si no tiene ninguna clase EventArgs personalizada, el tipo Event será el delegado EventHandler no genérico.  No necesita declarar el delegado porque ya está declarado en el espacio de nombres <xref:System> que se incluyó al crear el proyecto de C\#.  Agregue el código siguiente a la clase del publicador.  
  
        ```  
        public event EventHandler RaiseCustomEvent;  
        ```  
  
    2.  Si usa la versión no genérica de <xref:System.EventHandler> y tiene una clase personalizada derivada de <xref:System.EventArgs>, declare el evento dentro de la clase de publicación y use el delegado del paso 2 como tipo.  
  
        ```  
        public event CustomEventHandler RaiseCustomEvent;  
  
        ```  
  
    3.  Si utiliza la versión genérica, no necesita un delegado personalizado.  En lugar de ello, en la clase de publicación, especifique el tipo de evento como `EventHandler<CustomEventArgs>` y sustituya el nombre de su propia clase incluido entre corchetes angulares.  
  
        ```  
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;  
        ```  
  
## Ejemplo  
 En el ejemplo siguiente se muestran los pasos anteriores con una clase EventArgs personalizada y <xref:System.EventHandler%601> como tipo de evento.  
  
 [!code-cs[csProgGuideEvents#2](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-publish-events-that-conform-to-net-framework-guidelines_1.cs)]  
  
## Vea también  
 <xref:System.Delegate>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Eventos](../../../csharp/programming-guide/events/index.md)   
 [Delegados](../../../csharp/programming-guide/delegates/index.md)