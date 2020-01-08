---
title: Validación de la complejidad de las contraseñas
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: 49e6f79c13c94a3f2f6891b259c4bb2bec54ae6f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344520"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="b43bf-102">Tutorial: Validar la complejidad de las contraseñas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b43bf-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="b43bf-103">Este método comprueba algunas características de contraseña segura y actualiza un parámetro de cadena con información sobre las comprobaciones de errores en la contraseña.</span><span class="sxs-lookup"><span data-stu-id="b43bf-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="b43bf-104">Las contraseñas se pueden usar en un sistema seguro para autorizar a un usuario.</span><span class="sxs-lookup"><span data-stu-id="b43bf-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="b43bf-105">Sin embargo, las contraseñas deben ser difíciles de adivinar para usuarios no autorizados.</span><span class="sxs-lookup"><span data-stu-id="b43bf-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="b43bf-106">Los atacantes pueden utilizar un programa de *ataque de diccionario* , que recorre en iteración todas las palabras de un diccionario (o varios diccionarios en distintos idiomas) y comprueba si alguna de las palabras funciona como contraseña de un usuario.</span><span class="sxs-lookup"><span data-stu-id="b43bf-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="b43bf-107">Las contraseñas no seguras como "Betis" o "Mustang" se pueden adivinar rápidamente.</span><span class="sxs-lookup"><span data-stu-id="b43bf-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="b43bf-108">Contraseñas más seguras, como "? 'L1N3vaFiNdMeyeP@sSWerd! ', es mucho menos probable que se adivine.</span><span class="sxs-lookup"><span data-stu-id="b43bf-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="b43bf-109">Un sistema protegido por contraseña debe asegurarse de que los usuarios elijan contraseñas seguras.</span><span class="sxs-lookup"><span data-stu-id="b43bf-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="b43bf-110">Una contraseña segura es compleja (que contiene una combinación de mayúsculas, minúsculas, números y caracteres especiales) y no es una palabra.</span><span class="sxs-lookup"><span data-stu-id="b43bf-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="b43bf-111">En este ejemplo se muestra cómo comprobar la complejidad.</span><span class="sxs-lookup"><span data-stu-id="b43bf-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b43bf-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b43bf-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="b43bf-113">Código</span><span class="sxs-lookup"><span data-stu-id="b43bf-113">Code</span></span>  
 [!code-vb[VbVbcnRegEx#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="b43bf-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="b43bf-114">Compile the code</span></span>  
 <span data-ttu-id="b43bf-115">Llame a este método pasando la cadena que contiene la contraseña.</span><span class="sxs-lookup"><span data-stu-id="b43bf-115">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="b43bf-116">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="b43bf-116">This example requires:</span></span>  
  
- <span data-ttu-id="b43bf-117">Acceso a los miembros del espacio de nombres <xref:System.Text.RegularExpressions>.</span><span class="sxs-lookup"><span data-stu-id="b43bf-117">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="b43bf-118">Agregue una instrucción `Imports` si no hay nombres de miembros completos en el código.</span><span class="sxs-lookup"><span data-stu-id="b43bf-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="b43bf-119">Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="b43bf-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="b43bf-120">de seguridad</span><span class="sxs-lookup"><span data-stu-id="b43bf-120">Security</span></span>  
 <span data-ttu-id="b43bf-121">Si va a mover la contraseña a través de una red, debe usar un método seguro para transferir los datos.</span><span class="sxs-lookup"><span data-stu-id="b43bf-121">If you're moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="b43bf-122">Para obtener más información, vea [seguridad de aplicaciones Web de ASP.net](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b43bf-122">For more information, see [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span></span>
  
 <span data-ttu-id="b43bf-123">Puede mejorar la precisión de la función de `ValidatePassword` agregando comprobaciones de complejidad adicionales:</span><span class="sxs-lookup"><span data-stu-id="b43bf-123">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
- <span data-ttu-id="b43bf-124">Compare la contraseña y sus subcadenas con el nombre del usuario, el identificador de usuario y un diccionario definido por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b43bf-124">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="b43bf-125">Además, trate caracteres visualmente similares como equivalentes al realizar las comparaciones.</span><span class="sxs-lookup"><span data-stu-id="b43bf-125">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="b43bf-126">Por ejemplo, trate las letras "l" y "e" como equivalentes a los números "1" y "3".</span><span class="sxs-lookup"><span data-stu-id="b43bf-126">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
- <span data-ttu-id="b43bf-127">Si solo hay un carácter en mayúscula, asegúrese de que no sea el primer carácter de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="b43bf-127">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
- <span data-ttu-id="b43bf-128">Asegúrese de que los dos últimos caracteres de la contraseña son caracteres de letra.</span><span class="sxs-lookup"><span data-stu-id="b43bf-128">Make sure that the last two characters of the password are letter characters.</span></span>  
  
- <span data-ttu-id="b43bf-129">No permita contraseñas en las que todos los símbolos se escriban desde la fila superior del teclado.</span><span class="sxs-lookup"><span data-stu-id="b43bf-129">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b43bf-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="b43bf-130">See also</span></span>

- <xref:System.Text.RegularExpressions.Regex>
- <span data-ttu-id="b43bf-131">[Seguridad de aplicaciones Web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b43bf-131">[ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span></span>
