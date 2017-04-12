---
title: "Validar la complejidad de las contraseñas (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- String data type, validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e899900d60bddb83fb640abcc7f11f333c1af870
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a>Tutorial: Validar la complejidad de las contraseñas (Visual Basic)
Este método comprueba si hay algunas características de contraseña segura y actualiza un parámetro de cadena con información sobre las comprobaciones que la contraseña se produce un error.  
  
 Las contraseñas se pueden utilizar en un sistema seguro para autorizar a un usuario. Sin embargo, las contraseñas deben ser difíciles de adivinar usuarios no autorizados. Los atacantes pueden utilizar un *ataque de diccionario* programa, que recorre en iteración todas las palabras de un diccionario (o varios diccionarios en distintos idiomas) y prueba si alguna de las palabras funciona como contraseña de un usuario. Las contraseñas débiles como "Ferrari" o "Ferrari" se pueden averiguar rápidamente. ¿Contraseñas más seguras, como "? Se 'L1N3vaFiNdMeyeP@sSWerd! ", es mucho menos probable que adivinar. Un sistema protegido por contraseña debe asegurarse de que los usuarios elijan contraseñas seguras.  
  
 Una contraseña segura es compleja (contiene una mezcla de mayúsculas, minúsculas, numéricos y caracteres especiales) y no es una palabra. En este ejemplo se muestra cómo comprobar la complejidad.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="code"></a>Código  
 [!code-vb[1 VbVbcnRegEx](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Llamar a este método pasando la cadena que contiene esa contraseña.  
  
 Para este ejemplo se necesita:  
  
-   Acceso a los miembros de la <xref:System.Text.RegularExpressions>espacio de nombres.</xref:System.Text.RegularExpressions> Agregar un `Imports` instrucción si no se califica completamente los nombres de miembro en el código. Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="security"></a>Seguridad  
 Si está moviendo la contraseña a través de una red, debe utilizar un método seguro para transferir datos. Para obtener más información, consulte [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc).  
  
 Puede mejorar la precisión de la `ValidatePassword` función agregando comprobaciones de complejidad adicionales:  
  
-   Compare la contraseña y sus subcadenas con el nombre de usuario, el identificador de usuario y un diccionario definido por la aplicación. Además, tratar caracteres visualmente similares como equivalentes al realizar las comparaciones. Por ejemplo, considere las letras "l" y "e" como equivalentes a los números "1" y "3".  
  
-   Si hay sólo un carácter en mayúscula, asegúrese de que no es el primer carácter de la contraseña.  
  
-   Asegúrese de que los dos últimos caracteres de la contraseña son caracteres de letra.  
  
-   No se admiten contraseñas en el que se especifican todos los símbolos de la fila superior del teclado.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Text.RegularExpressions.Regex></xref:System.Text.RegularExpressions.Regex>   
 [Seguridad de aplicaciones Web ASP.NET](https://msdn.microsoft.com/library/330a99hc)
