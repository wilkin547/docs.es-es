---
title: Seguridad e introducción de datos por el usuario
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET Framework], user input
- user input, security
- secure coding, user input
- code security, user input
ms.assetid: 9141076a-96c9-4b01-93de-366bb1d858bc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 858ee30479c959f30673725b4ba8088fcc2d8f3b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33581760"
---
# <a name="security-and-user-input"></a><span data-ttu-id="6ffef-102">Seguridad e introducción de datos por el usuario</span><span class="sxs-lookup"><span data-stu-id="6ffef-102">Security and User Input</span></span>
<span data-ttu-id="6ffef-103">Los datos de usuario, que consisten en cualquier tipo de entrada (datos de una solicitud web o dirección URL, entrada a los controles de una aplicación de Microsoft Windows Forms etc.), pueden afectar negativamente al código, porque a menudo se utilizan esos datos directamente como parámetros para llamar a otro código.</span><span class="sxs-lookup"><span data-stu-id="6ffef-103">User data, which is any kind of input (data from a Web request or URL, input to controls of a Microsoft Windows Forms application, and so on), can adversely influence code because often that data is used directly as parameters to call other code.</span></span> <span data-ttu-id="6ffef-104">Esta situación es análoga al código malintencionado que llama a su código con parámetros extraños, y se deben tomar las mismas precauciones.</span><span class="sxs-lookup"><span data-stu-id="6ffef-104">This situation is analogous to malicious code calling your code with strange parameters, and the same precautions should be taken.</span></span> <span data-ttu-id="6ffef-105">La entrada del usuario es en realidad más difícil de proteger, porque no hay ningún marco de pila para realizar el seguimiento de la presencia de datos que no sean de confianza.</span><span class="sxs-lookup"><span data-stu-id="6ffef-105">User input is actually harder to make safe because there is no stack frame to trace the presence of the potentially untrusted data.</span></span>  
  
 <span data-ttu-id="6ffef-106">Estos son los errores de seguridad más sutiles y más difíciles de localizar porque, aunque pueden existir en el código aparentemente no relacionado con la seguridad, son una puerta de enlace para que pasen datos maliciosos a otro código.</span><span class="sxs-lookup"><span data-stu-id="6ffef-106">These are among the subtlest and hardest security bugs to find because, although they can exist in code that is seemingly unrelated to security, they are a gateway to pass bad data through to other code.</span></span> <span data-ttu-id="6ffef-107">Para buscar estos errores, siga cualquier tipo de datos de entrada, imagine cuál puede ser el intervalo de valores posibles y considere si el código que ve estos datos puede controlar todos esos casos.</span><span class="sxs-lookup"><span data-stu-id="6ffef-107">To look for these bugs, follow any kind of input data, imagine what the range of possible values might be, and consider whether the code seeing this data can handle all those cases.</span></span> <span data-ttu-id="6ffef-108">Puede corregir estos errores mediante la comprobación del intervalo y el rechazo de cualquier entrada que no puede controlar el código.</span><span class="sxs-lookup"><span data-stu-id="6ffef-108">You can fix these bugs through range checking and rejecting any input the code cannot handle.</span></span>  
  
 <span data-ttu-id="6ffef-109">A continuación se indican algunas consideraciones importantes que afectan a los datos de usuario:</span><span class="sxs-lookup"><span data-stu-id="6ffef-109">Some important considerations involving user data include the following:</span></span>  
  
-   <span data-ttu-id="6ffef-110">Los datos de usuario de una respuesta del servidor se ejecutan en el contexto del sitio del servidor en el cliente.</span><span class="sxs-lookup"><span data-stu-id="6ffef-110">Any user data in a server response runs in the context of the server's site on the client.</span></span> <span data-ttu-id="6ffef-111">Si el servidor web toma los datos de usuario y los inserta en la página web, podría incluir, por ejemplo, una etiqueta **\<script>** y ejecutarlos como si se encontrase en el servidor.</span><span class="sxs-lookup"><span data-stu-id="6ffef-111">If your Web server takes user data and inserts it into the returned Web page, it might, for example, include a **\<script>** tag and run as if from the server.</span></span>  
  
-   <span data-ttu-id="6ffef-112">Recuerde que el cliente puede solicitar cualquier dirección URL.</span><span class="sxs-lookup"><span data-stu-id="6ffef-112">Remember that the client can request any URL.</span></span>  
  
-   <span data-ttu-id="6ffef-113">Tenga en cuenta las rutas de acceso complicadas o no válidas:</span><span class="sxs-lookup"><span data-stu-id="6ffef-113">Consider tricky or invalid paths:</span></span>  
  
    -   <span data-ttu-id="6ffef-114">..\, rutas de acceso extremadamente largas.</span><span class="sxs-lookup"><span data-stu-id="6ffef-114">..\ , extremely long paths.</span></span>  
  
    -   <span data-ttu-id="6ffef-115">Uso de caracteres comodín (\*).</span><span class="sxs-lookup"><span data-stu-id="6ffef-115">Use of wild card characters (\*).</span></span>  
  
    -   <span data-ttu-id="6ffef-116">Expansión de token (%token%).</span><span class="sxs-lookup"><span data-stu-id="6ffef-116">Token expansion (%token%).</span></span>  
  
    -   <span data-ttu-id="6ffef-117">Formatos extraños de rutas de acceso con un significado especial.</span><span class="sxs-lookup"><span data-stu-id="6ffef-117">Strange forms of paths with special meaning.</span></span>  
  
    -   <span data-ttu-id="6ffef-118">Nombres de flujos de sistema de archivo alternativos, como `filename::$DATA`.</span><span class="sxs-lookup"><span data-stu-id="6ffef-118">Alternate file system stream names such as `filename::$DATA`.</span></span>  
  
    -   <span data-ttu-id="6ffef-119">Versiones cortas de los nombres de archivo como `longfi~1` para `longfilename`.</span><span class="sxs-lookup"><span data-stu-id="6ffef-119">Short versions of file names such as `longfi~1` for `longfilename`.</span></span>  
  
-   <span data-ttu-id="6ffef-120">Recuerde que Eval(userdata) puede hacer cualquier cosa.</span><span class="sxs-lookup"><span data-stu-id="6ffef-120">Remember that Eval(userdata) can do anything.</span></span>  
  
-   <span data-ttu-id="6ffef-121">Tenga cuidado de los enlaces tardíos en un nombre que incluye algunos datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="6ffef-121">Be wary of late binding to a name that includes some user data.</span></span>  
  
-   <span data-ttu-id="6ffef-122">Si está trabajando con datos de web, tenga en cuenta las distintas secuencias de escape permitidas, como:</span><span class="sxs-lookup"><span data-stu-id="6ffef-122">If you are dealing with Web data, consider the various forms of escapes that are permissible, including:</span></span>  
  
    -   <span data-ttu-id="6ffef-123">Secuencias de escape hexadecimales (%nn).</span><span class="sxs-lookup"><span data-stu-id="6ffef-123">Hexadecimal escapes (%nn).</span></span>  
  
    -   <span data-ttu-id="6ffef-124">Secuencias de escape Unicode (%nnn).</span><span class="sxs-lookup"><span data-stu-id="6ffef-124">Unicode escapes (%nnn).</span></span>  
  
    -   <span data-ttu-id="6ffef-125">Secuencias de escape UTF-8 excesivamente largas (%nn%nn).</span><span class="sxs-lookup"><span data-stu-id="6ffef-125">Overlong UTF-8 escapes (%nn%nn).</span></span>  
  
    -   <span data-ttu-id="6ffef-126">Secuencias de escape dobles (%nn se convierte en %mmnn, donde %mm es el escape para '%').</span><span class="sxs-lookup"><span data-stu-id="6ffef-126">Double escapes (%nn becomes %mmnn, where %mm is the escape for '%').</span></span>  
  
-   <span data-ttu-id="6ffef-127">Tenga cuidado con los nombres de usuario que pueden tener más de un formato canónico.</span><span class="sxs-lookup"><span data-stu-id="6ffef-127">Be wary of user names that might have more than one canonical format.</span></span> <span data-ttu-id="6ffef-128">Por ejemplo, a menudo puede utilizar cualquier forma de MIDOMINIO\\*nombreUsuario* o de *nombreUsuario*@mydomain.example.com.</span><span class="sxs-lookup"><span data-stu-id="6ffef-128">For example, you can often use either the MYDOMAIN\\*username* form or the *username*@mydomain.example.com form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ffef-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ffef-129">See Also</span></span>  
 [<span data-ttu-id="6ffef-130">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="6ffef-130">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
