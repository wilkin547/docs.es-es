---
title: "No est&#225; definido el tipo &#39;&lt;nombredetipo&gt;&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30002"
  - "bc30002"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30002"
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# No est&#225; definido el tipo &#39;&lt;nombredetipo&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

La instrucción hace referencia a un tipo que no está definido.  Se puede definir un tipo en una instrucción de declaración como `Enum`, `Structure`, `Class` o `Interface`.  
  
 **Identificador de error:** BC30002  
  
### Para corregir este error  
  
-   Asegúrese de que la definición de tipo y su referencia se escriben de la misma forma.  
  
-   Asegúrese de que la definición de tipo es accesible para la referencia.  Por ejemplo, si el tipo se encuentra en otro módulo y se ha declarado como `Private`, mueva la definición de tipo al módulo que contiene la referencia o declárelo como `Public`.  
  
-   Asegúrese de que el espacio de nombres del tipo no se ha vuelto a definir dentro de su proyecto.  Si es así, utilice la palabra clave `Global` para completar el nombre de tipo.  Por ejemplo, si un proyecto define un espacio de nombres denominado `System`, no se puede tener acceso al tipo <xref:System.Object?displayProperty=fullName> a menos que esté completo con la palabra clave `Global`: `Global.System.Object`.  
  
-   Si el tipo está definido, pero la biblioteca de objetos o de tipos en la que se ha definido no está registrada en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], haga clic en **Agregar referencia** en el menú **Proyecto** y, a continuación, seleccione la biblioteca de objetos o de tipos adecuada.  
  
-   Asegúrese de que el tipo está en un ensamblado que forma parte del perfil de .NET Framework de destino.  Para obtener más información, vea [Solucionar problemas de versión de .NET Framework de destino](/visual-studio/msbuild/troubleshooting-dotnet-framework-targeting-errors).  
  
## Vea también  
 [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Enum \(Instrucción\)](../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Structure \(Instrucción\)](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Class \(Instrucción\)](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Interface \(Instrucción\)](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Administrar referencias en un proyecto](/visual-studio/ide/managing-references-in-a-project)