---
title: "WriteOnly (Visual Basic) | Microsoft Docs"
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
  - "WriteOnly"
  - "vb.WriteOnly"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "propiedades [Visual Basic], de solo escritura"
  - "datos confidenciales"
  - "datos confidenciales, proteger"
  - "WriteOnly (palabra clave)"
  - "propiedades de solo escritura"
ms.assetid: 488d2899-b09f-4cee-92f0-6f9f9fc4f944
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# WriteOnly (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Especifica que se puede escribir pero no leer una propiedad.  
  
## Comentarios  
  
## Reglas  
 **Contexto de la declaración.** Sólo puede utilizar `WriteOnly` en el nivel de módulo.  Esto significa que el contexto de la declaración para una propiedad `WriteOnly` debe ser una clase, estructura o módulo y no puede ser un archivo de código fuente, espacio de nombres o procedimiento.  
  
 Puede declarar una propiedad como `WriteOnly`, pero no una variable.  
  
## Cuándo se utiliza WriteOnly  
 A veces desea que el código utilizado pueda establecer un valor pero sin detectar lo que es.  Por ejemplo, se deben proteger los datos sensibles, como números de registro social o contraseñas, para que no obtenga acceso a ellos ningún componente que no lo haya establecido.  En estos casos, puede utilizar una propiedad `WriteOnly` para establecer el valor.  
  
> [!IMPORTANT]
>  Cuando define y utiliza una propiedad `WriteOnly`, tenga en cuenta las medidas de protección adicionales siguientes:  
  
-   **Reemplazo.** Si la propiedad es un miembro de una clase, permita que tenga un valor predeterminado [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) y no la declare `Overridable` ni `MustOverride`.  Esto evita que una clase derivada tenga un acceso no deseado mediante un reemplazo.  
  
-   **Nivel de acceso.** Si tiene información confidencial de una propiedad en una o más variables, declárelas [Private](../../../visual-basic/language-reference/modifiers/private.md) para que ningún otro código pueda tener acceso a ellas.  
  
-   **Cifrado.** Almacene todos los datos sensibles en un formulario cifrado en lugar de en texto sin formato.  Si un código malintencionado obtiene acceso de algún modo a esa área de memoria, resulta más difícil utilizar los datos.  El cifrado también es útil si es necesario serializar los datos sensibles.  
  
-   **Restablecimiento.** Cuando se termina la clase, estructura o módulo que define la propiedad, restablezca los datos sensibles a los valores predeterminados o a otros valores sin significado.  Esto proporciona una protección adicional cuando esa área de memoria se libera para el acceso general.  
  
-   **Persistencia.** No conserve ningún dato sensible, por ejemplo en disco, si puede evitarlo.  Tampoco escriba ningún dato sensible en el Portapapeles.  
  
 El modificador `WriteOnly` se puede utilizar en este contexto:  
  
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## Vea también  
 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)