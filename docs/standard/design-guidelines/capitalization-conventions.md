---
title: Normas referentes al uso de minúsculas y mayúsculas
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
ms.openlocfilehash: 8af4a15e1e5b34c38b14c6b547cf44801bbf13e6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741759"
---
# <a name="capitalization-conventions"></a><span data-ttu-id="33463-102">Normas referentes al uso de minúsculas y mayúsculas</span><span class="sxs-lookup"><span data-stu-id="33463-102">Capitalization Conventions</span></span>
<span data-ttu-id="33463-103">En las instrucciones de este capítulo se diseña un método sencillo para usar el caso que, cuando se aplica de forma coherente, facilitan la lectura de los identificadores de tipos, miembros y parámetros.</span><span class="sxs-lookup"><span data-stu-id="33463-103">The guidelines in this chapter lay out a simple method for using case that, when applied consistently, make identifiers for types, members, and parameters easy to read.</span></span>

## <a name="capitalization-rules-for-identifiers"></a><span data-ttu-id="33463-104">Reglas de mayúsculas y minúsculas para identificadores</span><span class="sxs-lookup"><span data-stu-id="33463-104">Capitalization Rules for Identifiers</span></span>
 <span data-ttu-id="33463-105">Para diferenciar las palabras en un identificador, ponga en mayúscula la primera letra de cada palabra en el identificador.</span><span class="sxs-lookup"><span data-stu-id="33463-105">To differentiate words in an identifier, capitalize the first letter of each word in the identifier.</span></span> <span data-ttu-id="33463-106">No utilice guiones bajos para diferenciar palabras o, en ese caso, en cualquier parte de los identificadores.</span><span class="sxs-lookup"><span data-stu-id="33463-106">Do not use underscores to differentiate words, or for that matter, anywhere in identifiers.</span></span> <span data-ttu-id="33463-107">Hay dos formas adecuadas de poner en mayúsculas los identificadores, dependiendo del uso del identificador:</span><span class="sxs-lookup"><span data-stu-id="33463-107">There are two appropriate ways to capitalize identifiers, depending on the use of the identifier:</span></span>

- <span data-ttu-id="33463-108">PascalCasing</span><span class="sxs-lookup"><span data-stu-id="33463-108">PascalCasing</span></span>

- <span data-ttu-id="33463-109">Alterne</span><span class="sxs-lookup"><span data-stu-id="33463-109">camelCasing</span></span>

 <span data-ttu-id="33463-110">La Convención PascalCasing, que se usa para todos los identificadores excepto los nombres de parámetro, pone en mayúsculas el primer carácter de cada palabra (incluidos los acrónimos de dos letras de longitud), como se muestra en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="33463-110">The PascalCasing convention, used for all identifiers except parameter names, capitalizes the first character of each word (including acronyms over two letters in length), as shown in the following examples:</span></span>

 `PropertyDescriptor`
 `HtmlTag`

 <span data-ttu-id="33463-111">Se crea un caso especial para los acrónimos de dos letras en los que ambas letras están en mayúsculas, como se muestra en el siguiente identificador:</span><span class="sxs-lookup"><span data-stu-id="33463-111">A special case is made for two-letter acronyms in which both letters are capitalized, as shown in the following identifier:</span></span>

 `IOStream`

 <span data-ttu-id="33463-112">La Convención alterne, que solo se usa para nombres de parámetro, pone en mayúsculas el primer carácter de cada palabra excepto la primera palabra, como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="33463-112">The camelCasing convention, used only for parameter names, capitalizes the first character of each word except the first word, as shown in the following examples.</span></span> <span data-ttu-id="33463-113">Como también se muestra en el ejemplo, los acrónimos de dos letras que comienzan un identificador con grafía Camel están en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="33463-113">As the example also shows, two-letter acronyms that begin a camel-cased identifier are both lowercase.</span></span>

 `propertyDescriptor`
 `ioStream`
 `htmlTag`

 <span data-ttu-id="33463-114">✔️ usar PascalCasing para todos los nombres de miembros públicos, tipos y espacios de nombres que se componen de varias palabras.</span><span class="sxs-lookup"><span data-stu-id="33463-114">✔️ DO use PascalCasing for all public member, type, and namespace names consisting of multiple words.</span></span>

 <span data-ttu-id="33463-115">✔️ usar alterne para los nombres de parámetro.</span><span class="sxs-lookup"><span data-stu-id="33463-115">✔️ DO use camelCasing for parameter names.</span></span>

 <span data-ttu-id="33463-116">En la tabla siguiente se describen las reglas de mayúsculas y minúsculas para los distintos tipos de identificadores.</span><span class="sxs-lookup"><span data-stu-id="33463-116">The following table describes the capitalization rules for different types of identifiers.</span></span>

|<span data-ttu-id="33463-117">Identificador</span><span class="sxs-lookup"><span data-stu-id="33463-117">Identifier</span></span>|<span data-ttu-id="33463-118">Uso de mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="33463-118">Casing</span></span>|<span data-ttu-id="33463-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33463-119">Example</span></span>|
|----------------|------------|-------------|
|<span data-ttu-id="33463-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="33463-120">Namespace</span></span>|<span data-ttu-id="33463-121">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="33463-121">Pascal</span></span>|`namespace System.Security { ... }`|
|<span data-ttu-id="33463-122">Tipo</span><span class="sxs-lookup"><span data-stu-id="33463-122">Type</span></span>|<span data-ttu-id="33463-123">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="33463-123">Pascal</span></span>|`public class StreamReader { ... }`|
|<span data-ttu-id="33463-124">Interfaz</span><span class="sxs-lookup"><span data-stu-id="33463-124">Interface</span></span>|<span data-ttu-id="33463-125">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="33463-125">Pascal</span></span>|`public interface IEnumerable { ... }`|
|<span data-ttu-id="33463-126">Método</span><span class="sxs-lookup"><span data-stu-id="33463-126">Method</span></span>|<span data-ttu-id="33463-127">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="33463-127">Pascal</span></span>|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|
|<span data-ttu-id="33463-128">Propiedad</span><span class="sxs-lookup"><span data-stu-id="33463-128">Property</span></span>|<span data-ttu-id="33463-129">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="33463-129">Pascal</span></span>|`public class String {` <br />  `public int Length { get; }` <br /> `}`|
|<span data-ttu-id="33463-130">Evento</span><span class="sxs-lookup"><span data-stu-id="33463-130">Event</span></span>|<span data-ttu-id="33463-131">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="33463-131">Pascal</span></span>|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|
|<span data-ttu-id="33463-132">Campo</span><span class="sxs-lookup"><span data-stu-id="33463-132">Field</span></span>|<span data-ttu-id="33463-133">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="33463-133">Pascal</span></span>|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|
|<span data-ttu-id="33463-134">Valor de enumeración</span><span class="sxs-lookup"><span data-stu-id="33463-134">Enum value</span></span>|<span data-ttu-id="33463-135">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="33463-135">Pascal</span></span>|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|
|<span data-ttu-id="33463-136">Parámetro</span><span class="sxs-lookup"><span data-stu-id="33463-136">Parameter</span></span>|<span data-ttu-id="33463-137">camelcase</span><span class="sxs-lookup"><span data-stu-id="33463-137">Camel</span></span>|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|

## <a name="capitalizing-compound-words-and-common-terms"></a><span data-ttu-id="33463-138">Poner en mayúsculas palabras compuestas y términos comunes</span><span class="sxs-lookup"><span data-stu-id="33463-138">Capitalizing Compound Words and Common Terms</span></span>
 <span data-ttu-id="33463-139">La mayoría de los términos compuestos se tratan como palabras únicas para el uso de mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="33463-139">Most compound terms are treated as single words for purposes of capitalization.</span></span>

 <span data-ttu-id="33463-140">❌ no poner en mayúsculas cada palabra en lo que se denomina palabras compuestas de formato cerrado.</span><span class="sxs-lookup"><span data-stu-id="33463-140">❌ DO NOT capitalize each word in so-called closed-form compound words.</span></span>

 <span data-ttu-id="33463-141">Se trata de palabras compuestas escritas como una sola palabra, como el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="33463-141">These are compound words written as a single word, such as endpoint.</span></span> <span data-ttu-id="33463-142">En lo que respecta a las directrices de mayúsculas y minúsculas, trate una palabra compuesta de formato cerrado como una sola palabra.</span><span class="sxs-lookup"><span data-stu-id="33463-142">For the purpose of casing guidelines, treat a closed-form compound word as a single word.</span></span> <span data-ttu-id="33463-143">Use un diccionario actual para determinar si una palabra compuesta está escrita en formato cerrado.</span><span class="sxs-lookup"><span data-stu-id="33463-143">Use a current dictionary to determine if a compound word is written in closed form.</span></span>

|<span data-ttu-id="33463-144">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="33463-144">Pascal</span></span>|<span data-ttu-id="33463-145">camelcase</span><span class="sxs-lookup"><span data-stu-id="33463-145">Camel</span></span>|<span data-ttu-id="33463-146">Not</span><span class="sxs-lookup"><span data-stu-id="33463-146">Not</span></span>|
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

## <a name="case-sensitivity"></a><span data-ttu-id="33463-147">Distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="33463-147">Case Sensitivity</span></span>
 <span data-ttu-id="33463-148">No es necesario que los lenguajes que se pueden ejecutar en CLR admitan la distinción de mayúsculas y minúsculas, aunque algunos sí lo hacen.</span><span class="sxs-lookup"><span data-stu-id="33463-148">Languages that can run on the CLR are not required to support case-sensitivity, although some do.</span></span> <span data-ttu-id="33463-149">Aunque su lenguaje lo admita, otros lenguajes que puedan tener acceso a su marco de trabajo no lo admiten.</span><span class="sxs-lookup"><span data-stu-id="33463-149">Even if your language supports it, other languages that might access your framework do not.</span></span> <span data-ttu-id="33463-150">Por lo tanto, las API a las que se puede tener acceso externamente no pueden basarse solo en mayúsculas y minúsculas para distinguir entre dos nombres en el mismo contexto.</span><span class="sxs-lookup"><span data-stu-id="33463-150">Any APIs that are externally accessible, therefore, cannot rely on case alone to distinguish between two names in the same context.</span></span>

 <span data-ttu-id="33463-151">❌ no suponen que todos los lenguajes de programación distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="33463-151">❌ DO NOT assume that all programming languages are case sensitive.</span></span> <span data-ttu-id="33463-152">pero no lo son.</span><span class="sxs-lookup"><span data-stu-id="33463-152">They are not.</span></span> <span data-ttu-id="33463-153">Los nombres no pueden diferir solo en mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="33463-153">Names cannot differ by case alone.</span></span>

 <span data-ttu-id="33463-154">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="33463-154">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="33463-155">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="33463-155">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="33463-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33463-156">See also</span></span>

- [<span data-ttu-id="33463-157">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="33463-157">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="33463-158">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="33463-158">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
