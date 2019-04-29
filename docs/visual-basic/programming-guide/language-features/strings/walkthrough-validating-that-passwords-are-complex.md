---
title: Validar la complejidad de contraseñas (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: 829d6485acdca22fbf10160c734e5c7f931dd855
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938260"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="629be-102">Tutorial: Validar la complejidad de contraseñas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="629be-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="629be-103">Este método comprueba si hay algunas características de contraseña segura y actualiza un parámetro de cadena con información sobre las comprobaciones que la contraseña se produce un error.</span><span class="sxs-lookup"><span data-stu-id="629be-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="629be-104">En un sistema seguro, se pueden usar contraseñas para autorizar a un usuario.</span><span class="sxs-lookup"><span data-stu-id="629be-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="629be-105">Sin embargo, las contraseñas deben ser difíciles para los usuarios no autorizados averigüen.</span><span class="sxs-lookup"><span data-stu-id="629be-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="629be-106">Los atacantes pueden usar un *ataque de diccionario* programa, que recorre en iteración todas las palabras en un diccionario (o varios diccionarios en distintos idiomas) y comprueba si cualquiera de las palabras funcionan como una contraseña de usuario.</span><span class="sxs-lookup"><span data-stu-id="629be-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="629be-107">Las contraseñas débiles como "Ferrari" o "Mustang" se pueden adivinar rápidamente.</span><span class="sxs-lookup"><span data-stu-id="629be-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="629be-108">¿Contraseñas más seguras, como "? Se 'L1N3vaFiNdMeyeP@sSWerd! ", es mucho menos probable que sea de adivinar.</span><span class="sxs-lookup"><span data-stu-id="629be-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="629be-109">Un sistema protegido por contraseña debe asegurarse de que los usuarios elegir contraseñas seguras.</span><span class="sxs-lookup"><span data-stu-id="629be-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="629be-110">Una contraseña segura es compleja (que contiene una combinación de caracteres en mayúsculas, minúsculas, numéricos y especiales) y no es una palabra.</span><span class="sxs-lookup"><span data-stu-id="629be-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="629be-111">En este ejemplo se muestra cómo comprobar la complejidad.</span><span class="sxs-lookup"><span data-stu-id="629be-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="629be-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="629be-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="629be-113">Código</span><span class="sxs-lookup"><span data-stu-id="629be-113">Code</span></span>  
 [!code-vb[VbVbcnRegEx#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="629be-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="629be-114">Compiling the Code</span></span>  
 <span data-ttu-id="629be-115">Llame a este método, pase la cadena que contiene esa contraseña.</span><span class="sxs-lookup"><span data-stu-id="629be-115">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="629be-116">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="629be-116">This example requires:</span></span>  
  
- <span data-ttu-id="629be-117">Acceso a los miembros del espacio de nombres <xref:System.Text.RegularExpressions>.</span><span class="sxs-lookup"><span data-stu-id="629be-117">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="629be-118">Agregue una instrucción `Imports` si no hay nombres de miembros completos en el código.</span><span class="sxs-lookup"><span data-stu-id="629be-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="629be-119">Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="629be-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="629be-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="629be-120">Security</span></span>  
 <span data-ttu-id="629be-121">Si te estás cambiando la contraseña a través de una red, deberá usar un método seguro de transferencia de datos.</span><span class="sxs-lookup"><span data-stu-id="629be-121">If you're moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="629be-122">Para obtener más información, consulte [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="629be-122">For more information, see [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span></span>
  
 <span data-ttu-id="629be-123">Puede mejorar la precisión de la `ValidatePassword` función agregando comprobaciones de complejidad adicional:</span><span class="sxs-lookup"><span data-stu-id="629be-123">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
- <span data-ttu-id="629be-124">Compare la contraseña y sus subcadenas contra un diccionario definido por la aplicación, identificador de usuario y el nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="629be-124">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="629be-125">Además, tratar caracteres visualmente similares como equivalentes cuando se realizan las comparaciones.</span><span class="sxs-lookup"><span data-stu-id="629be-125">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="629be-126">Por ejemplo, se tratan las letras "l" y "e" como equivalentes a los números "1" y "3".</span><span class="sxs-lookup"><span data-stu-id="629be-126">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
- <span data-ttu-id="629be-127">Si hay un solo carácter en mayúscula, asegúrese de que no es el primer carácter de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="629be-127">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
- <span data-ttu-id="629be-128">Asegúrese de que los dos últimos caracteres de la contraseña son caracteres de letras.</span><span class="sxs-lookup"><span data-stu-id="629be-128">Make sure that the last two characters of the password are letter characters.</span></span>  
  
- <span data-ttu-id="629be-129">No se admiten contraseñas en el que se especifican todos los símbolos de la fila superior del teclado.</span><span class="sxs-lookup"><span data-stu-id="629be-129">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="629be-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="629be-130">See also</span></span>

- <xref:System.Text.RegularExpressions.Regex>
- <span data-ttu-id="629be-131">[Seguridad de aplicaciones Web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="629be-131">[ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span></span>
