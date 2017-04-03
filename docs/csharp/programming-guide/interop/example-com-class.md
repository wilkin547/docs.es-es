---
title: "Clases COM de ejemplo (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- examples [C#], COM classes
- COM, exposing Visual C# objects to
ms.assetid: 6504dea9-ad1c-4993-a794-830fec5270af
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2525d322bf3284c82356253d1383edbcd3928084
ms.lasthandoff: 03/13/2017

---
# <a name="example-com-class-c-programming-guide"></a>Clases COM de ejemplo (Guía de programación de C#)
El siguiente es un ejemplo de una clase que se expondría como un objeto COM. Una vez insertado este código de ejemplo en un archivo .cs y agregado al proyecto, establezca la propiedad **Registrar para interoperabilidad COM** en **True**. Para obtener más información, vea [NIB: Cómo: Registrar un componente para interoperabilidad COM](http://msdn.microsoft.com/en-us/4de7d474-56e8-4027-994d-d47ca4725c5e).  
  
 Exponer objetos de Visual C# para COM requiere declarar una interfaz de clase, una interfaz de eventos si es necesario y la propia clase. Los miembros de clase deben seguir estas reglas para que sean visibles en COM:  
  
-   La clase debe ser pública.  
  
-   Las propiedades, métodos y eventos deben ser públicos.  
  
-   Las propiedades y métodos deben declararse en la interfaz de clase.  
  
-   Los eventos deben declararse en la interfaz de eventos.  
  
 Los demás miembros públicos de la clase que no se declaren en estas interfaces no serán visibles para COM, pero lo serán para el resto de objetos de .NET Framework.  
  
 Para exponer propiedades y métodos en COM, se deben declarar en la interfaz de clase y marcar con el atributo `DispId`, e implementarlos en la clase. El orden en que se declaran los miembros en la interfaz es el orden usado para la tabla virtual de COM.  
  
 Para exponer los eventos de la clase, se deben declarar en la interfaz de eventos y marcarlos con un atributo `DispId`. La clase no debe implementar esta interfaz.  
  
 La clase implementa la interfaz de clase y puede implementar más de una interfaz, pero la primera implementación debe ser la interfaz de clase predeterminada. Implemente los métodos y propiedades expuestos para COM aquí. Deben marcarse como públicos y coincidir con las declaraciones de la interfaz de clase. Asimismo, declare los eventos iniciados por la clase aquí. Deben marcarse como públicos y coincidir con las declaraciones de la interfaz de eventos.  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csProgGuideInterop#8](../../../csharp/programming-guide/interop/codesnippet/CSharp/example-com-class_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Interoperabilidad](../../../csharp/programming-guide/interop/index.md)   
 [Página Compilar (Diseñador de proyectos) (C#)](https://docs.microsoft.com/visualstudio/ide/reference/build-page-project-designer-csharp)
