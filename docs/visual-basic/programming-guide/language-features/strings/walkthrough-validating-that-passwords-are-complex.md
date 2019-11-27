---
title: Validación de la complejidad de las contraseñas
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: 6e8697379a6fbb5cc15b60291e5b822897c2c013
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348332"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a>Tutorial: Validar la complejidad de las contraseñas (Visual Basic)
Este método comprueba algunas características de contraseña segura y actualiza un parámetro de cadena con información sobre las comprobaciones de errores en la contraseña.  
  
 Las contraseñas se pueden usar en un sistema seguro para autorizar a un usuario. Sin embargo, las contraseñas deben ser difíciles de adivinar para usuarios no autorizados. Los atacantes pueden utilizar un programa de *ataque de diccionario* , que recorre en iteración todas las palabras de un diccionario (o varios diccionarios en distintos idiomas) y comprueba si alguna de las palabras funciona como contraseña de un usuario. Las contraseñas no seguras como "Betis" o "Mustang" se pueden adivinar rápidamente. Contraseñas más seguras, como "? 'L1N3vaFiNdMeyeP@sSWerd! ', es mucho menos probable que se adivine. Un sistema protegido por contraseña debe asegurarse de que los usuarios elijan contraseñas seguras.  
  
 Una contraseña segura es compleja (que contiene una combinación de mayúsculas, minúsculas, números y caracteres especiales) y no es una palabra. En este ejemplo se muestra cómo comprobar la complejidad.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="code"></a>Código  
 [!code-vb[VbVbcnRegEx#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Llame a este método pasando la cadena que contiene la contraseña.  
  
 Para este ejemplo se necesita:  
  
- Acceso a los miembros del espacio de nombres <xref:System.Text.RegularExpressions>. Agregue una instrucción `Imports` si no hay nombres de miembros completos en el código. Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="security"></a>Seguridad  
 Si va a mover la contraseña a través de una red, debe usar un método seguro para transferir los datos. Para obtener más información, vea [seguridad de aplicaciones Web de ASP.net](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).
  
 Puede mejorar la precisión de la función de `ValidatePassword` agregando comprobaciones de complejidad adicionales:  
  
- Compare la contraseña y sus subcadenas con el nombre del usuario, el identificador de usuario y un diccionario definido por la aplicación. Además, trate caracteres visualmente similares como equivalentes al realizar las comparaciones. Por ejemplo, trate las letras "l" y "e" como equivalentes a los números "1" y "3".  
  
- Si solo hay un carácter en mayúscula, asegúrese de que no sea el primer carácter de la contraseña.  
  
- Asegúrese de que los dos últimos caracteres de la contraseña son caracteres de letra.  
  
- No permita contraseñas en las que todos los símbolos se escriban desde la fila superior del teclado.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Text.RegularExpressions.Regex>
- [Seguridad de aplicaciones Web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))
