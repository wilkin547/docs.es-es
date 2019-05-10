---
title: Validar la complejidad de contraseñas (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: ff0ac933be917b5604966240ff1fbd331a34ba77
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663628"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a>Tutorial: Validar la complejidad de contraseñas (Visual Basic)
Este método comprueba si hay algunas características de contraseña segura y actualiza un parámetro de cadena con información sobre las comprobaciones que la contraseña se produce un error.  
  
 En un sistema seguro, se pueden usar contraseñas para autorizar a un usuario. Sin embargo, las contraseñas deben ser difíciles para los usuarios no autorizados averigüen. Los atacantes pueden usar un *ataque de diccionario* programa, que recorre en iteración todas las palabras en un diccionario (o varios diccionarios en distintos idiomas) y comprueba si cualquiera de las palabras funcionan como una contraseña de usuario. Las contraseñas débiles como "Ferrari" o "Mustang" se pueden adivinar rápidamente. ¿Contraseñas más seguras, como "? Se 'L1N3vaFiNdMeyeP@sSWerd! ", es mucho menos probable que sea de adivinar. Un sistema protegido por contraseña debe asegurarse de que los usuarios elegir contraseñas seguras.  
  
 Una contraseña segura es compleja (que contiene una combinación de caracteres en mayúsculas, minúsculas, numéricos y especiales) y no es una palabra. En este ejemplo se muestra cómo comprobar la complejidad.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="code"></a>Código  
 [!code-vb[VbVbcnRegEx#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Llame a este método, pase la cadena que contiene esa contraseña.  
  
 Para este ejemplo se necesita:  
  
- Acceso a los miembros del espacio de nombres <xref:System.Text.RegularExpressions>. Agregue una instrucción `Imports` si no hay nombres de miembros completos en el código. Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="security"></a>Seguridad  
 Si te estás cambiando la contraseña a través de una red, deberá usar un método seguro de transferencia de datos. Para obtener más información, consulte [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).
  
 Puede mejorar la precisión de la `ValidatePassword` función agregando comprobaciones de complejidad adicional:  
  
- Compare la contraseña y sus subcadenas contra un diccionario definido por la aplicación, identificador de usuario y el nombre del usuario. Además, tratar caracteres visualmente similares como equivalentes cuando se realizan las comparaciones. Por ejemplo, se tratan las letras "l" y "e" como equivalentes a los números "1" y "3".  
  
- Si hay un solo carácter en mayúscula, asegúrese de que no es el primer carácter de la contraseña.  
  
- Asegúrese de que los dos últimos caracteres de la contraseña son caracteres de letras.  
  
- No se admiten contraseñas en el que se especifican todos los símbolos de la fila superior del teclado.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Text.RegularExpressions.Regex>
- [Seguridad de aplicaciones Web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))
