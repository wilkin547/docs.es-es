---
title: "Validar la complejidad de contraseñas (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bdbe5f385c6b7a0898c4907b0d8afabdaed06fa0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="748f2-102">Tutorial: Validar la complejidad de las contraseñas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="748f2-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="748f2-103">Este método comprueba si hay algunas características de contraseña segura y actualiza un parámetro de cadena con información sobre las comprobaciones que la contraseña se produce un error.</span><span class="sxs-lookup"><span data-stu-id="748f2-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="748f2-104">Las contraseñas pueden utilizarse en un sistema seguro para autorizar a un usuario.</span><span class="sxs-lookup"><span data-stu-id="748f2-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="748f2-105">Sin embargo, las contraseñas deben ser difíciles para los usuarios no autorizados averigüen.</span><span class="sxs-lookup"><span data-stu-id="748f2-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="748f2-106">Los atacantes pueden utilizar un *ataque de diccionario* programa, que recorre en iteración todas las palabras de un diccionario (o varios diccionarios en distintos idiomas) y comprueba si cualquiera de las palabras funciona como contraseña de un usuario.</span><span class="sxs-lookup"><span data-stu-id="748f2-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="748f2-107">Las contraseñas débiles como "Ferrari" o "Ferrari" se pueden averiguar rápidamente.</span><span class="sxs-lookup"><span data-stu-id="748f2-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="748f2-108">¿Contraseñas más seguras, como "? Se 'L1N3vaFiNdMeyeP@sSWerd! ", es mucho menos probable que pueda descifrar.</span><span class="sxs-lookup"><span data-stu-id="748f2-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="748f2-109">Un sistema de protección por contraseña debe asegurarse de que los usuarios elegir contraseñas seguras.</span><span class="sxs-lookup"><span data-stu-id="748f2-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="748f2-110">Una contraseña segura es compleja (contiene una mezcla de caracteres en mayúsculas, minúsculas, numéricos y especiales) y no es una palabra.</span><span class="sxs-lookup"><span data-stu-id="748f2-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="748f2-111">En este ejemplo se muestra cómo comprobar que la complejidad.</span><span class="sxs-lookup"><span data-stu-id="748f2-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="748f2-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="748f2-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="748f2-113">Código</span><span class="sxs-lookup"><span data-stu-id="748f2-113">Code</span></span>  
 [!code-vb[VbVbcnRegEx#1](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="748f2-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="748f2-114">Compiling the Code</span></span>  
 <span data-ttu-id="748f2-115">Llamar a este método pasando la cadena que contiene esa contraseña.</span><span class="sxs-lookup"><span data-stu-id="748f2-115">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="748f2-116">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="748f2-116">This example requires:</span></span>  
  
-   <span data-ttu-id="748f2-117">Acceso a los miembros del espacio de nombres <xref:System.Text.RegularExpressions>.</span><span class="sxs-lookup"><span data-stu-id="748f2-117">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="748f2-118">Agregue una instrucción `Imports` si no hay nombres de miembros completos en el código.</span><span class="sxs-lookup"><span data-stu-id="748f2-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="748f2-119">Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="748f2-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="748f2-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="748f2-120">Security</span></span>  
 <span data-ttu-id="748f2-121">Si va a mover la contraseña a través de una red, debe usar un método seguro de transferencia de datos.</span><span class="sxs-lookup"><span data-stu-id="748f2-121">If you are moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="748f2-122">Para obtener más información, consulte [seguridad de la aplicación Web ASP.NET](https://msdn.microsoft.com/library/330a99hc).</span><span class="sxs-lookup"><span data-stu-id="748f2-122">For more information, see [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc).</span></span>  
  
 <span data-ttu-id="748f2-123">Puede mejorar la precisión de la `ValidatePassword` función agregando comprobaciones de complejidad adicionales:</span><span class="sxs-lookup"><span data-stu-id="748f2-123">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
-   <span data-ttu-id="748f2-124">Compare la contraseña y sus subcadenas en el nombre del usuario, el identificador de usuario y un diccionario definido por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="748f2-124">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="748f2-125">Además, tratar caracteres visualmente similares como equivalentes al realizar las comparaciones.</span><span class="sxs-lookup"><span data-stu-id="748f2-125">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="748f2-126">Por ejemplo, considere las letras "l" y "e" como equivalentes a los números "1" y "3".</span><span class="sxs-lookup"><span data-stu-id="748f2-126">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
-   <span data-ttu-id="748f2-127">Si hay un solo carácter en mayúscula, asegúrese de que no es el primer carácter de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="748f2-127">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
-   <span data-ttu-id="748f2-128">Asegúrese de que los dos últimos caracteres de la contraseña son caracteres de letras.</span><span class="sxs-lookup"><span data-stu-id="748f2-128">Make sure that the last two characters of the password are letter characters.</span></span>  
  
-   <span data-ttu-id="748f2-129">No se admiten contraseñas en el que se especifican todos los símbolos de la fila superior del teclado.</span><span class="sxs-lookup"><span data-stu-id="748f2-129">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="748f2-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="748f2-130">See Also</span></span>  
 <xref:System.Text.RegularExpressions.Regex>  
 [<span data-ttu-id="748f2-131">Seguridad de aplicaciones Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="748f2-131">ASP.NET Web Application Security</span></span>](https://msdn.microsoft.com/library/330a99hc)
