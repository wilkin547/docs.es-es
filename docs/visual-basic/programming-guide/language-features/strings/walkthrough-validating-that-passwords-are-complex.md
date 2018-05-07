---
title: Validar la complejidad de contraseñas (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: acfc8ab958c8671ed7f1afd245d24a43ca12be29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a>Tutorial: Validar la complejidad de las contraseñas (Visual Basic)
Este método comprueba si hay algunas características de contraseña segura y actualiza un parámetro de cadena con información sobre las comprobaciones que la contraseña se produce un error.  
  
 Las contraseñas pueden utilizarse en un sistema seguro para autorizar a un usuario. Sin embargo, las contraseñas deben ser difíciles para los usuarios no autorizados averigüen. Los atacantes pueden utilizar un *ataque de diccionario* programa, que recorre en iteración todas las palabras de un diccionario (o varios diccionarios en distintos idiomas) y comprueba si cualquiera de las palabras funciona como contraseña de un usuario. Las contraseñas débiles como "Ferrari" o "Ferrari" se pueden averiguar rápidamente. ¿Contraseñas más seguras, como "? Se 'L1N3vaFiNdMeyeP@sSWerd! ", es mucho menos probable que pueda descifrar. Un sistema de protección por contraseña debe asegurarse de que los usuarios elegir contraseñas seguras.  
  
 Una contraseña segura es compleja (contiene una mezcla de caracteres en mayúsculas, minúsculas, numéricos y especiales) y no es una palabra. En este ejemplo se muestra cómo comprobar que la complejidad.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="code"></a>Código  
 [!code-vb[VbVbcnRegEx#1](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Llamar a este método pasando la cadena que contiene esa contraseña.  
  
 Para este ejemplo se necesita:  
  
-   Acceso a los miembros del espacio de nombres <xref:System.Text.RegularExpressions>. Agregue una instrucción `Imports` si no hay nombres de miembros completos en el código. Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="security"></a>Seguridad  
 Si va a mover la contraseña a través de una red, debe usar un método seguro de transferencia de datos. Para obtener más información, consulte [seguridad de la aplicación Web ASP.NET](https://msdn.microsoft.com/library/330a99hc).  
  
 Puede mejorar la precisión de la `ValidatePassword` función agregando comprobaciones de complejidad adicionales:  
  
-   Compare la contraseña y sus subcadenas en el nombre del usuario, el identificador de usuario y un diccionario definido por la aplicación. Además, tratar caracteres visualmente similares como equivalentes al realizar las comparaciones. Por ejemplo, considere las letras "l" y "e" como equivalentes a los números "1" y "3".  
  
-   Si hay un solo carácter en mayúscula, asegúrese de que no es el primer carácter de la contraseña.  
  
-   Asegúrese de que los dos últimos caracteres de la contraseña son caracteres de letras.  
  
-   No se admiten contraseñas en el que se especifican todos los símbolos de la fila superior del teclado.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Text.RegularExpressions.Regex>  
 [Seguridad de aplicaciones Web ASP.NET](https://msdn.microsoft.com/library/330a99hc)
