---
title: Normas referentes al uso de minúsculas y mayúsculas
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 070fc69728c2cb38e465dab9f6f591a77a857531
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47089028"
---
# <a name="capitalization-conventions"></a><span data-ttu-id="063df-102">Normas referentes al uso de minúsculas y mayúsculas</span><span class="sxs-lookup"><span data-stu-id="063df-102">Capitalization Conventions</span></span>
<span data-ttu-id="063df-103">Las directrices descritas en este capítulo disponer un método sencillo para el uso de caso de que, cuando se aplica de forma coherente, asegúrese de identificadores para los tipos, miembros y parámetros fáciles de leer.</span><span class="sxs-lookup"><span data-stu-id="063df-103">The guidelines in this chapter lay out a simple method for using case that, when applied consistently, make identifiers for types, members, and parameters easy to read.</span></span>  
  
## <a name="capitalization-rules-for-identifiers"></a><span data-ttu-id="063df-104">Reglas de mayúsculas y minúsculas para los identificadores</span><span class="sxs-lookup"><span data-stu-id="063df-104">Capitalization Rules for Identifiers</span></span>  
 <span data-ttu-id="063df-105">Para diferenciar las palabras en un identificador, poner en mayúsculas la primera letra de cada palabra en el identificador.</span><span class="sxs-lookup"><span data-stu-id="063df-105">To differentiate words in an identifier, capitalize the first letter of each word in the identifier.</span></span> <span data-ttu-id="063df-106">No utilice caracteres de subrayado para diferenciar las palabras, o bien, de hecho, en cualquier lugar en los identificadores.</span><span class="sxs-lookup"><span data-stu-id="063df-106">Do not use underscores to differentiate words, or for that matter, anywhere in identifiers.</span></span> <span data-ttu-id="063df-107">Hay dos maneras adecuados para aprovechar los identificadores, según el uso del identificador:</span><span class="sxs-lookup"><span data-stu-id="063df-107">There are two appropriate ways to capitalize identifiers, depending on the use of the identifier:</span></span>  
  
-   <span data-ttu-id="063df-108">Pascal</span><span class="sxs-lookup"><span data-stu-id="063df-108">PascalCasing</span></span>  
  
-   <span data-ttu-id="063df-109">mayúsculas intercaladas</span><span class="sxs-lookup"><span data-stu-id="063df-109">camelCasing</span></span>  
  
 <span data-ttu-id="063df-110">La convención Pascal, usada para todos los identificadores, excepto los nombres de parámetro, se pone en mayúsculas el primer carácter de cada palabra (incluidos los acrónimos a través de dos letras de longitud), tal como se muestra en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="063df-110">The PascalCasing convention, used for all identifiers except parameter names, capitalizes the first character of each word (including acronyms over two letters in length), as shown in the following examples:</span></span>  
  
 `PropertyDescriptor`  
 `HtmlTag`  
  
 <span data-ttu-id="063df-111">Un caso especial se realiza para los acrónimos de dos letras en el que se escriben dos letras, como se muestra en el siguiente identificador:</span><span class="sxs-lookup"><span data-stu-id="063df-111">A special case is made for two-letter acronyms in which both letters are capitalized, as shown in the following identifier:</span></span>  
  
 `IOStream`  
  
 <span data-ttu-id="063df-112">La convención camelCasing, usa solo para los nombres de parámetro, se pone en mayúsculas el primer carácter de cada palabra, excepto la primera palabra, como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="063df-112">The camelCasing convention, used only for parameter names, capitalizes the first character of each word except the first word, as shown in the following examples.</span></span> <span data-ttu-id="063df-113">Como también se muestra en el ejemplo, son las siglas de dos letras que comenzar un identificador con grafía camel tanto en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="063df-113">As the example also shows, two-letter acronyms that begin a camel-cased identifier are both lowercase.</span></span>  
  
 `propertyDescriptor`  
 `ioStream`  
 `htmlTag`  
  
 <span data-ttu-id="063df-114">**✓ DO** usar Pascal para todos los nombres de miembro, el tipo y el espacio de nombres públicos que consta de varias palabras.</span><span class="sxs-lookup"><span data-stu-id="063df-114">**✓ DO** use PascalCasing for all public member, type, and namespace names consisting of multiple words.</span></span>  
  
 <span data-ttu-id="063df-115">**✓ DO** utilice seguir el estilo Camel para los nombres de parámetro.</span><span class="sxs-lookup"><span data-stu-id="063df-115">**✓ DO** use camelCasing for parameter names.</span></span>  
  
 <span data-ttu-id="063df-116">En la tabla siguiente describe las reglas de mayúsculas y minúsculas para diferentes tipos de identificadores.</span><span class="sxs-lookup"><span data-stu-id="063df-116">The following table describes the capitalization rules for different types of identifiers.</span></span>  
  
|<span data-ttu-id="063df-117">Identificador</span><span class="sxs-lookup"><span data-stu-id="063df-117">Identifier</span></span>|<span data-ttu-id="063df-118">Mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="063df-118">Casing</span></span>|<span data-ttu-id="063df-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="063df-119">Example</span></span>|  
|----------------|------------|-------------|  
|<span data-ttu-id="063df-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="063df-120">Namespace</span></span>|<span data-ttu-id="063df-121">Pascal</span><span class="sxs-lookup"><span data-stu-id="063df-121">Pascal</span></span>|`namespace System.Security { ... }`|  
|<span data-ttu-id="063df-122">Tipo</span><span class="sxs-lookup"><span data-stu-id="063df-122">Type</span></span>|<span data-ttu-id="063df-123">Pascal</span><span class="sxs-lookup"><span data-stu-id="063df-123">Pascal</span></span>|`public class StreamReader { ... }`|  
|<span data-ttu-id="063df-124">Interfaz</span><span class="sxs-lookup"><span data-stu-id="063df-124">Interface</span></span>|<span data-ttu-id="063df-125">Pascal</span><span class="sxs-lookup"><span data-stu-id="063df-125">Pascal</span></span>|`public interface IEnumerable { ... }`|  
|<span data-ttu-id="063df-126">Método</span><span class="sxs-lookup"><span data-stu-id="063df-126">Method</span></span>|<span data-ttu-id="063df-127">Pascal</span><span class="sxs-lookup"><span data-stu-id="063df-127">Pascal</span></span>|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|  
|<span data-ttu-id="063df-128">Property</span><span class="sxs-lookup"><span data-stu-id="063df-128">Property</span></span>|<span data-ttu-id="063df-129">Pascal</span><span class="sxs-lookup"><span data-stu-id="063df-129">Pascal</span></span>|`public class String {` <br />  `public int Length { get; }` <br /> `}`|  
|<span data-ttu-id="063df-130">evento</span><span class="sxs-lookup"><span data-stu-id="063df-130">Event</span></span>|<span data-ttu-id="063df-131">Pascal</span><span class="sxs-lookup"><span data-stu-id="063df-131">Pascal</span></span>|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|  
|<span data-ttu-id="063df-132">Campo</span><span class="sxs-lookup"><span data-stu-id="063df-132">Field</span></span>|<span data-ttu-id="063df-133">Pascal</span><span class="sxs-lookup"><span data-stu-id="063df-133">Pascal</span></span>|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|  
|<span data-ttu-id="063df-134">Valor de enumeración</span><span class="sxs-lookup"><span data-stu-id="063df-134">Enum value</span></span>|<span data-ttu-id="063df-135">Pascal</span><span class="sxs-lookup"><span data-stu-id="063df-135">Pascal</span></span>|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|  
|<span data-ttu-id="063df-136">Parámetro</span><span class="sxs-lookup"><span data-stu-id="063df-136">Parameter</span></span>|<span data-ttu-id="063df-137">Camel</span><span class="sxs-lookup"><span data-stu-id="063df-137">Camel</span></span>|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|  
  
## <a name="capitalizing-compound-words-and-common-terms"></a><span data-ttu-id="063df-138">Uso de mayúsculas para las palabras compuestas y términos comunes</span><span class="sxs-lookup"><span data-stu-id="063df-138">Capitalizing Compound Words and Common Terms</span></span>  
 <span data-ttu-id="063df-139">La mayoría de los términos compuestos se tratan como palabras únicas para los fines de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="063df-139">Most compound terms are treated as single words for purposes of capitalization.</span></span>  
  
 <span data-ttu-id="063df-140">**X DO NOT** poner en mayúsculas cada palabra en denominadas palabras compuestas con formato cerrado.</span><span class="sxs-lookup"><span data-stu-id="063df-140">**X DO NOT** capitalize each word in so-called closed-form compound words.</span></span>  
  
 <span data-ttu-id="063df-141">Estas son las palabras compuestas que se escribe como una sola palabra, como punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="063df-141">These are compound words written as a single word, such as endpoint.</span></span> <span data-ttu-id="063df-142">Con el fin de las directrices de mayúsculas y minúsculas, tratar una palabra compuesta de formulario cerrado como una sola palabra.</span><span class="sxs-lookup"><span data-stu-id="063df-142">For the purpose of casing guidelines, treat a closed-form compound word as a single word.</span></span> <span data-ttu-id="063df-143">Usar un diccionario actual para determinar si se escribe una palabra compuesta en forma cerrada.</span><span class="sxs-lookup"><span data-stu-id="063df-143">Use a current dictionary to determine if a compound word is written in closed form.</span></span>  
  
|<span data-ttu-id="063df-144">Pascal</span><span class="sxs-lookup"><span data-stu-id="063df-144">Pascal</span></span>|<span data-ttu-id="063df-145">Camel</span><span class="sxs-lookup"><span data-stu-id="063df-145">Camel</span></span>|<span data-ttu-id="063df-146">no</span><span class="sxs-lookup"><span data-stu-id="063df-146">Not</span></span>|  
|------------|-----------|---------|  
|`BitFlag`|`bitFlag`|`Bitflag`|  
|`Callback`|`callback`|`CallBack`|  
|`Canceled`|`canceled`|`Cancelled`|  
|`DoNot`|`doNot`|`Don't`|  
|`Email`|`email`|`EMail`|  
|`Endpoint`|`endpoint`|`EndPoint`|  
|`FileName`|`fileName`|`Filename`|  
|`Gridline`|`gridline`|`GridLine`|  
|`Hashtable`|`hashtable`|`HashTable`|  
|`Id`|`id`|`ID`|  
|`Indexes`|`indexes`|`Indices`|  
|`LogOff`|`logOff`|`LogOut`|  
|`LogOn`|`logOn`|`LogIn`|  
|`Metadata`|`metadata`|`MetaData, metaData`|  
|`Multipanel`|`multipanel`|`MultiPanel`|  
|`Multiview`|`multiview`|`MultiView`|  
|`Namespace`|`namespace`|`NameSpace`|  
|`Ok`|`ok`|`OK`|  
|`Pi`|`pi`|`PI`|  
|`Placeholder`|`placeholder`|`PlaceHolder`|  
|`SignIn`|`signIn`|`SignOn`|  
|`SignOut`|`signOut`|`SignOff`|  
|`UserName`|`userName`|`Username`|  
|`WhiteSpace`|`whiteSpace`|`Whitespace`|  
|`Writable`|`writable`|`Writeable`|  
  
## <a name="case-sensitivity"></a><span data-ttu-id="063df-147">Distinción de mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="063df-147">Case Sensitivity</span></span>  
 <span data-ttu-id="063df-148">Los idiomas que se pueden ejecutar en el CLR no tienen que admitir minúsculas, aunque algunos.</span><span class="sxs-lookup"><span data-stu-id="063df-148">Languages that can run on the CLR are not required to support case-sensitivity, although some do.</span></span> <span data-ttu-id="063df-149">Incluso si su lenguaje lo admite, otros lenguajes que podrían tener acceso a su marco de trabajo no lo hacen.</span><span class="sxs-lookup"><span data-stu-id="063df-149">Even if your language supports it, other languages that might access your framework do not.</span></span> <span data-ttu-id="063df-150">Ninguna API que es accesible externamente, por lo tanto, no puede confiar en caso de por sí solo para distinguir entre los dos nombres en el mismo contexto.</span><span class="sxs-lookup"><span data-stu-id="063df-150">Any APIs that are externally accessible, therefore, cannot rely on case alone to distinguish between two names in the same context.</span></span>  
  
 <span data-ttu-id="063df-151">**X DO NOT** se supone que todos los lenguajes de programación distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="063df-151">**X DO NOT** assume that all programming languages are case sensitive.</span></span> <span data-ttu-id="063df-152">pero no lo son.</span><span class="sxs-lookup"><span data-stu-id="063df-152">They are not.</span></span> <span data-ttu-id="063df-153">Los nombres no pueden diferenciarse por el caso de por sí solo.</span><span class="sxs-lookup"><span data-stu-id="063df-153">Names cannot differ by case alone.</span></span>  
  
 <span data-ttu-id="063df-154">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="063df-154">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="063df-155">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="063df-155">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="063df-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="063df-156">See also</span></span>

- [<span data-ttu-id="063df-157">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="063df-157">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="063df-158">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="063df-158">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
