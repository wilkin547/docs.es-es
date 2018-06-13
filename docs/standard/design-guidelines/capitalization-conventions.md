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
ms.openlocfilehash: 7ef7913a2601c3a791cb028b4074ce37b9e9421b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575289"
---
# <a name="capitalization-conventions"></a><span data-ttu-id="6c09f-102">Normas referentes al uso de minúsculas y mayúsculas</span><span class="sxs-lookup"><span data-stu-id="6c09f-102">Capitalization Conventions</span></span>
<span data-ttu-id="6c09f-103">Las directrices descritas en este capítulo disponer un método sencillo para el uso de mayúsculas, cuando se aplica de forma coherente, asegúrese de identificadores para los tipos, miembros y parámetros fáciles de leer.</span><span class="sxs-lookup"><span data-stu-id="6c09f-103">The guidelines in this chapter lay out a simple method for using case that, when applied consistently, make identifiers for types, members, and parameters easy to read.</span></span>  
  
## <a name="capitalization-rules-for-identifiers"></a><span data-ttu-id="6c09f-104">Reglas de mayúsculas y minúsculas para los identificadores</span><span class="sxs-lookup"><span data-stu-id="6c09f-104">Capitalization Rules for Identifiers</span></span>  
 <span data-ttu-id="6c09f-105">Para diferenciar las palabras en un identificador, poner en mayúscula la primera letra de cada palabra en el identificador.</span><span class="sxs-lookup"><span data-stu-id="6c09f-105">To differentiate words in an identifier, capitalize the first letter of each word in the identifier.</span></span> <span data-ttu-id="6c09f-106">No use caracteres de subrayado para diferenciar las palabras o con este propósito, en cualquier lugar en los identificadores.</span><span class="sxs-lookup"><span data-stu-id="6c09f-106">Do not use underscores to differentiate words, or for that matter, anywhere in identifiers.</span></span> <span data-ttu-id="6c09f-107">Hay dos maneras adecuados aprovechar identificadores, según el uso del identificador:</span><span class="sxs-lookup"><span data-stu-id="6c09f-107">There are two appropriate ways to capitalize identifiers, depending on the use of the identifier:</span></span>  
  
-   <span data-ttu-id="6c09f-108">Pascal</span><span class="sxs-lookup"><span data-stu-id="6c09f-108">PascalCasing</span></span>  
  
-   <span data-ttu-id="6c09f-109">seguir el estilo Camel</span><span class="sxs-lookup"><span data-stu-id="6c09f-109">camelCasing</span></span>  
  
 <span data-ttu-id="6c09f-110">La convención Pascal, utilizada para todos los identificadores excepto los nombres de parámetro, se pone en mayúsculas el primer carácter de cada palabra (incluidos los acrónimos a través de dos letras de longitud), tal como se muestra en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6c09f-110">The PascalCasing convention, used for all identifiers except parameter names, capitalizes the first character of each word (including acronyms over two letters in length), as shown in the following examples:</span></span>  
  
 `PropertyDescriptor`  
 `HtmlTag`  
  
 <span data-ttu-id="6c09f-111">Se ha realizado un caso especial para los acrónimos de dos letras en el que están en dos letras en mayúscula, como se muestra en el siguiente identificador:</span><span class="sxs-lookup"><span data-stu-id="6c09f-111">A special case is made for two-letter acronyms in which both letters are capitalized, as shown in the following identifier:</span></span>  
  
 `IOStream`  
  
 <span data-ttu-id="6c09f-112">La convención de seguir el estilo Camel, usar solo para los nombres de parámetro, pone en mayúsculas el primer carácter de cada palabra excepto la primera palabra, como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="6c09f-112">The camelCasing convention, used only for parameter names, capitalizes the first character of each word except the first word, as shown in the following examples.</span></span> <span data-ttu-id="6c09f-113">Como también se muestra en el ejemplo, acrónimos de dos letras que comenzar un identificador con grafía camel son en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6c09f-113">As the example also shows, two-letter acronyms that begin a camel-cased identifier are both lowercase.</span></span>  
  
 `propertyDescriptor`  
 `ioStream`  
 `htmlTag`  
  
 <span data-ttu-id="6c09f-114">**✓ HACER** usar Pascal para todos los nombres de miembro, el tipo y el espacio de nombres públicos que consta de varias palabras.</span><span class="sxs-lookup"><span data-stu-id="6c09f-114">**✓ DO** use PascalCasing for all public member, type, and namespace names consisting of multiple words.</span></span>  
  
 <span data-ttu-id="6c09f-115">**✓ HACER** utilice seguir el estilo Camel para los nombres de parámetro.</span><span class="sxs-lookup"><span data-stu-id="6c09f-115">**✓ DO** use camelCasing for parameter names.</span></span>  
  
 <span data-ttu-id="6c09f-116">En la tabla siguiente describe las reglas de mayúsculas y minúsculas para diferentes tipos de identificadores.</span><span class="sxs-lookup"><span data-stu-id="6c09f-116">The following table describes the capitalization rules for different types of identifiers.</span></span>  
  
|<span data-ttu-id="6c09f-117">Identificador</span><span class="sxs-lookup"><span data-stu-id="6c09f-117">Identifier</span></span>|<span data-ttu-id="6c09f-118">Mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="6c09f-118">Casing</span></span>|<span data-ttu-id="6c09f-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6c09f-119">Example</span></span>|  
|----------------|------------|-------------|  
|<span data-ttu-id="6c09f-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="6c09f-120">Namespace</span></span>|<span data-ttu-id="6c09f-121">Pascal</span><span class="sxs-lookup"><span data-stu-id="6c09f-121">Pascal</span></span>|`namespace System.Security { ... }`|  
|<span data-ttu-id="6c09f-122">Tipo</span><span class="sxs-lookup"><span data-stu-id="6c09f-122">Type</span></span>|<span data-ttu-id="6c09f-123">Pascal</span><span class="sxs-lookup"><span data-stu-id="6c09f-123">Pascal</span></span>|`public class StreamReader { ... }`|  
|<span data-ttu-id="6c09f-124">Interfaz</span><span class="sxs-lookup"><span data-stu-id="6c09f-124">Interface</span></span>|<span data-ttu-id="6c09f-125">Pascal</span><span class="sxs-lookup"><span data-stu-id="6c09f-125">Pascal</span></span>|`public interface IEnumerable { ... }`|  
|<span data-ttu-id="6c09f-126">Método</span><span class="sxs-lookup"><span data-stu-id="6c09f-126">Method</span></span>|<span data-ttu-id="6c09f-127">Pascal</span><span class="sxs-lookup"><span data-stu-id="6c09f-127">Pascal</span></span>|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|  
|<span data-ttu-id="6c09f-128">Property</span><span class="sxs-lookup"><span data-stu-id="6c09f-128">Property</span></span>|<span data-ttu-id="6c09f-129">Pascal</span><span class="sxs-lookup"><span data-stu-id="6c09f-129">Pascal</span></span>|`public class String {` <br />  `public int Length { get; }` <br /> `}`|  
|<span data-ttu-id="6c09f-130">evento</span><span class="sxs-lookup"><span data-stu-id="6c09f-130">Event</span></span>|<span data-ttu-id="6c09f-131">Pascal</span><span class="sxs-lookup"><span data-stu-id="6c09f-131">Pascal</span></span>|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|  
|<span data-ttu-id="6c09f-132">Campo</span><span class="sxs-lookup"><span data-stu-id="6c09f-132">Field</span></span>|<span data-ttu-id="6c09f-133">Pascal</span><span class="sxs-lookup"><span data-stu-id="6c09f-133">Pascal</span></span>|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|  
|<span data-ttu-id="6c09f-134">Valor de enumeración</span><span class="sxs-lookup"><span data-stu-id="6c09f-134">Enum value</span></span>|<span data-ttu-id="6c09f-135">Pascal</span><span class="sxs-lookup"><span data-stu-id="6c09f-135">Pascal</span></span>|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|  
|<span data-ttu-id="6c09f-136">Parámetro</span><span class="sxs-lookup"><span data-stu-id="6c09f-136">Parameter</span></span>|<span data-ttu-id="6c09f-137">Camel</span><span class="sxs-lookup"><span data-stu-id="6c09f-137">Camel</span></span>|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|  
  
## <a name="capitalizing-compound-words-and-common-terms"></a><span data-ttu-id="6c09f-138">Poner en mayúsculas palabras compuestas y términos comunes</span><span class="sxs-lookup"><span data-stu-id="6c09f-138">Capitalizing Compound Words and Common Terms</span></span>  
 <span data-ttu-id="6c09f-139">La mayoría de términos compuestos se tratan como palabras individuales para los fines de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6c09f-139">Most compound terms are treated as single words for purposes of capitalization.</span></span>  
  
 <span data-ttu-id="6c09f-140">**X DO NOT** poner en mayúsculas cada palabra en denominadas palabras compuestas con formato cerrado.</span><span class="sxs-lookup"><span data-stu-id="6c09f-140">**X DO NOT** capitalize each word in so-called closed-form compound words.</span></span>  
  
 <span data-ttu-id="6c09f-141">Éstas son palabras compuestas que se escribe como una sola palabra, como punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="6c09f-141">These are compound words written as a single word, such as endpoint.</span></span> <span data-ttu-id="6c09f-142">Con el fin de obtener instrucciones de mayúsculas y minúsculas, tratar una palabra compuesta con formato cerrado como una sola palabra.</span><span class="sxs-lookup"><span data-stu-id="6c09f-142">For the purpose of casing guidelines, treat a closed-form compound word as a single word.</span></span> <span data-ttu-id="6c09f-143">Use un diccionario actual para determinar si se escribe una palabra compuesta en forma cerrada.</span><span class="sxs-lookup"><span data-stu-id="6c09f-143">Use a current dictionary to determine if a compound word is written in closed form.</span></span>  
  
|<span data-ttu-id="6c09f-144">Pascal</span><span class="sxs-lookup"><span data-stu-id="6c09f-144">Pascal</span></span>|<span data-ttu-id="6c09f-145">Camel</span><span class="sxs-lookup"><span data-stu-id="6c09f-145">Camel</span></span>|<span data-ttu-id="6c09f-146">No</span><span class="sxs-lookup"><span data-stu-id="6c09f-146">Not</span></span>|  
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
  
## <a name="case-sensitivity"></a><span data-ttu-id="6c09f-147">Distinción de mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="6c09f-147">Case Sensitivity</span></span>  
 <span data-ttu-id="6c09f-148">Lenguajes que se pueden ejecutar en el CLR no se necesitan para admitir esta característica, aunque algunos no.</span><span class="sxs-lookup"><span data-stu-id="6c09f-148">Languages that can run on the CLR are not required to support case-sensitivity, although some do.</span></span> <span data-ttu-id="6c09f-149">Incluso si el idioma lo admite, otros lenguajes que pueden tener acceso el marco no lo hace.</span><span class="sxs-lookup"><span data-stu-id="6c09f-149">Even if your language supports it, other languages that might access your framework do not.</span></span> <span data-ttu-id="6c09f-150">Ninguna API que esté accesible desde el exterior, por lo tanto, no se puede confiar en el caso de por sí solo para distinguir entre los dos nombres en el mismo contexto.</span><span class="sxs-lookup"><span data-stu-id="6c09f-150">Any APIs that are externally accessible, therefore, cannot rely on case alone to distinguish between two names in the same context.</span></span>  
  
 <span data-ttu-id="6c09f-151">**X DO NOT** se supone que todos los lenguajes de programación distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6c09f-151">**X DO NOT** assume that all programming languages are case sensitive.</span></span> <span data-ttu-id="6c09f-152">pero no lo son.</span><span class="sxs-lookup"><span data-stu-id="6c09f-152">They are not.</span></span> <span data-ttu-id="6c09f-153">Los nombres no pueden diferenciarse por sólo por sus mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="6c09f-153">Names cannot differ by case alone.</span></span>  
  
 <span data-ttu-id="6c09f-154">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="6c09f-154">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6c09f-155">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="6c09f-155">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c09f-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c09f-156">See Also</span></span>  
 [<span data-ttu-id="6c09f-157">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6c09f-157">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="6c09f-158">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="6c09f-158">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
