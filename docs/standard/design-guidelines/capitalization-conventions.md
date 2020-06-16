---
title: Normas referentes al uso de minúsculas y mayúsculas
description: Aplicar convenciones de mayúsculas y minúsculas para los identificadores, las palabras compuestas y los términos comunes. Comprenda cómo funciona la distinción de mayúsculas y minúsculas en .NET.
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
ms.openlocfilehash: 4903dc587d84ef36bfaa641cfbda59484266c23c
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84767798"
---
# <a name="capitalization-conventions"></a><span data-ttu-id="b57ef-104">Normas referentes al uso de minúsculas y mayúsculas</span><span class="sxs-lookup"><span data-stu-id="b57ef-104">Capitalization Conventions</span></span>
<span data-ttu-id="b57ef-105">En las instrucciones de este capítulo se diseña un método sencillo para usar el caso que, cuando se aplica de forma coherente, facilitan la lectura de los identificadores de tipos, miembros y parámetros.</span><span class="sxs-lookup"><span data-stu-id="b57ef-105">The guidelines in this chapter lay out a simple method for using case that, when applied consistently, make identifiers for types, members, and parameters easy to read.</span></span>

## <a name="capitalization-rules-for-identifiers"></a><span data-ttu-id="b57ef-106">Reglas de mayúsculas y minúsculas para identificadores</span><span class="sxs-lookup"><span data-stu-id="b57ef-106">Capitalization Rules for Identifiers</span></span>
 <span data-ttu-id="b57ef-107">Para diferenciar las palabras en un identificador, ponga en mayúscula la primera letra de cada palabra en el identificador.</span><span class="sxs-lookup"><span data-stu-id="b57ef-107">To differentiate words in an identifier, capitalize the first letter of each word in the identifier.</span></span> <span data-ttu-id="b57ef-108">No utilice guiones bajos para diferenciar palabras o, en ese caso, en cualquier parte de los identificadores.</span><span class="sxs-lookup"><span data-stu-id="b57ef-108">Do not use underscores to differentiate words, or for that matter, anywhere in identifiers.</span></span> <span data-ttu-id="b57ef-109">Hay dos formas adecuadas de poner en mayúsculas los identificadores, dependiendo del uso del identificador:</span><span class="sxs-lookup"><span data-stu-id="b57ef-109">There are two appropriate ways to capitalize identifiers, depending on the use of the identifier:</span></span>

- <span data-ttu-id="b57ef-110">PascalCasing</span><span class="sxs-lookup"><span data-stu-id="b57ef-110">PascalCasing</span></span>

- <span data-ttu-id="b57ef-111">Alterne</span><span class="sxs-lookup"><span data-stu-id="b57ef-111">camelCasing</span></span>

 <span data-ttu-id="b57ef-112">La Convención PascalCasing, que se usa para todos los identificadores excepto los nombres de parámetro, pone en mayúsculas el primer carácter de cada palabra (incluidos los acrónimos de dos letras de longitud), como se muestra en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b57ef-112">The PascalCasing convention, used for all identifiers except parameter names, capitalizes the first character of each word (including acronyms over two letters in length), as shown in the following examples:</span></span>

 `PropertyDescriptor`
 `HtmlTag`

 <span data-ttu-id="b57ef-113">Se crea un caso especial para los acrónimos de dos letras en los que ambas letras están en mayúsculas, como se muestra en el siguiente identificador:</span><span class="sxs-lookup"><span data-stu-id="b57ef-113">A special case is made for two-letter acronyms in which both letters are capitalized, as shown in the following identifier:</span></span>

 `IOStream`

 <span data-ttu-id="b57ef-114">La Convención alterne, que solo se usa para nombres de parámetro, pone en mayúsculas el primer carácter de cada palabra excepto la primera palabra, como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="b57ef-114">The camelCasing convention, used only for parameter names, capitalizes the first character of each word except the first word, as shown in the following examples.</span></span> <span data-ttu-id="b57ef-115">Como también se muestra en el ejemplo, los acrónimos de dos letras que comienzan un identificador con grafía Camel están en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b57ef-115">As the example also shows, two-letter acronyms that begin a camel-cased identifier are both lowercase.</span></span>

 `propertyDescriptor`
 `ioStream`
 `htmlTag`

 <span data-ttu-id="b57ef-116">✔️ usar PascalCasing para todos los nombres de miembros públicos, tipos y espacios de nombres que se componen de varias palabras.</span><span class="sxs-lookup"><span data-stu-id="b57ef-116">✔️ DO use PascalCasing for all public member, type, and namespace names consisting of multiple words.</span></span>

 <span data-ttu-id="b57ef-117">✔️ usar alterne para los nombres de parámetro.</span><span class="sxs-lookup"><span data-stu-id="b57ef-117">✔️ DO use camelCasing for parameter names.</span></span>

 <span data-ttu-id="b57ef-118">En la tabla siguiente se describen las reglas de mayúsculas y minúsculas para los distintos tipos de identificadores.</span><span class="sxs-lookup"><span data-stu-id="b57ef-118">The following table describes the capitalization rules for different types of identifiers.</span></span>

|<span data-ttu-id="b57ef-119">Identificador</span><span class="sxs-lookup"><span data-stu-id="b57ef-119">Identifier</span></span>|<span data-ttu-id="b57ef-120">Uso de mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="b57ef-120">Casing</span></span>|<span data-ttu-id="b57ef-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b57ef-121">Example</span></span>|
|----------------|------------|-------------|
|<span data-ttu-id="b57ef-122">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="b57ef-122">Namespace</span></span>|<span data-ttu-id="b57ef-123">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="b57ef-123">Pascal</span></span>|`namespace System.Security { ... }`|
|<span data-ttu-id="b57ef-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="b57ef-124">Type</span></span>|<span data-ttu-id="b57ef-125">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="b57ef-125">Pascal</span></span>|`public class StreamReader { ... }`|
|<span data-ttu-id="b57ef-126">Interfaz</span><span class="sxs-lookup"><span data-stu-id="b57ef-126">Interface</span></span>|<span data-ttu-id="b57ef-127">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="b57ef-127">Pascal</span></span>|`public interface IEnumerable { ... }`|
|<span data-ttu-id="b57ef-128">Método</span><span class="sxs-lookup"><span data-stu-id="b57ef-128">Method</span></span>|<span data-ttu-id="b57ef-129">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="b57ef-129">Pascal</span></span>|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|
|<span data-ttu-id="b57ef-130">Propiedad</span><span class="sxs-lookup"><span data-stu-id="b57ef-130">Property</span></span>|<span data-ttu-id="b57ef-131">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="b57ef-131">Pascal</span></span>|`public class String {` <br />  `public int Length { get; }` <br /> `}`|
|<span data-ttu-id="b57ef-132">Evento</span><span class="sxs-lookup"><span data-stu-id="b57ef-132">Event</span></span>|<span data-ttu-id="b57ef-133">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="b57ef-133">Pascal</span></span>|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|
|<span data-ttu-id="b57ef-134">Campo</span><span class="sxs-lookup"><span data-stu-id="b57ef-134">Field</span></span>|<span data-ttu-id="b57ef-135">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="b57ef-135">Pascal</span></span>|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|
|<span data-ttu-id="b57ef-136">Valor de enumeración</span><span class="sxs-lookup"><span data-stu-id="b57ef-136">Enum value</span></span>|<span data-ttu-id="b57ef-137">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="b57ef-137">Pascal</span></span>|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|
|<span data-ttu-id="b57ef-138">Parámetro</span><span class="sxs-lookup"><span data-stu-id="b57ef-138">Parameter</span></span>|<span data-ttu-id="b57ef-139">camelcase</span><span class="sxs-lookup"><span data-stu-id="b57ef-139">Camel</span></span>|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|

## <a name="capitalizing-compound-words-and-common-terms"></a><span data-ttu-id="b57ef-140">Poner en mayúsculas palabras compuestas y términos comunes</span><span class="sxs-lookup"><span data-stu-id="b57ef-140">Capitalizing Compound Words and Common Terms</span></span>
 <span data-ttu-id="b57ef-141">La mayoría de los términos compuestos se tratan como palabras únicas para el uso de mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="b57ef-141">Most compound terms are treated as single words for purposes of capitalization.</span></span>

 <span data-ttu-id="b57ef-142">❌No ponga en mayúsculas cada palabra en lo que se denomina palabras compuestas de formato cerrado.</span><span class="sxs-lookup"><span data-stu-id="b57ef-142">❌ DO NOT capitalize each word in so-called closed-form compound words.</span></span>

 <span data-ttu-id="b57ef-143">Se trata de palabras compuestas escritas como una sola palabra, como el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b57ef-143">These are compound words written as a single word, such as endpoint.</span></span> <span data-ttu-id="b57ef-144">En lo que respecta a las directrices de mayúsculas y minúsculas, trate una palabra compuesta de formato cerrado como una sola palabra.</span><span class="sxs-lookup"><span data-stu-id="b57ef-144">For the purpose of casing guidelines, treat a closed-form compound word as a single word.</span></span> <span data-ttu-id="b57ef-145">Use un diccionario actual para determinar si una palabra compuesta está escrita en formato cerrado.</span><span class="sxs-lookup"><span data-stu-id="b57ef-145">Use a current dictionary to determine if a compound word is written in closed form.</span></span>

|<span data-ttu-id="b57ef-146">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="b57ef-146">Pascal</span></span>|<span data-ttu-id="b57ef-147">camelcase</span><span class="sxs-lookup"><span data-stu-id="b57ef-147">Camel</span></span>|<span data-ttu-id="b57ef-148">Not</span><span class="sxs-lookup"><span data-stu-id="b57ef-148">Not</span></span>|
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

## <a name="case-sensitivity"></a><span data-ttu-id="b57ef-149">Distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="b57ef-149">Case Sensitivity</span></span>
 <span data-ttu-id="b57ef-150">No es necesario que los lenguajes que se pueden ejecutar en CLR admitan la distinción de mayúsculas y minúsculas, aunque algunos sí lo hacen.</span><span class="sxs-lookup"><span data-stu-id="b57ef-150">Languages that can run on the CLR are not required to support case-sensitivity, although some do.</span></span> <span data-ttu-id="b57ef-151">Aunque su lenguaje lo admita, otros lenguajes que puedan tener acceso a su marco de trabajo no lo admiten.</span><span class="sxs-lookup"><span data-stu-id="b57ef-151">Even if your language supports it, other languages that might access your framework do not.</span></span> <span data-ttu-id="b57ef-152">Por lo tanto, las API a las que se puede tener acceso externamente no pueden basarse solo en mayúsculas y minúsculas para distinguir entre dos nombres en el mismo contexto.</span><span class="sxs-lookup"><span data-stu-id="b57ef-152">Any APIs that are externally accessible, therefore, cannot rely on case alone to distinguish between two names in the same context.</span></span>

 <span data-ttu-id="b57ef-153">❌NO asuma que todos los lenguajes de programación distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b57ef-153">❌ DO NOT assume that all programming languages are case sensitive.</span></span> <span data-ttu-id="b57ef-154">pero no lo son.</span><span class="sxs-lookup"><span data-stu-id="b57ef-154">They are not.</span></span> <span data-ttu-id="b57ef-155">Los nombres no pueden diferir solo en mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b57ef-155">Names cannot differ by case alone.</span></span>

 <span data-ttu-id="b57ef-156">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="b57ef-156">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="b57ef-157">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="b57ef-157">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="b57ef-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b57ef-158">See also</span></span>

- [<span data-ttu-id="b57ef-159">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="b57ef-159">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="b57ef-160">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="b57ef-160">Naming Guidelines</span></span>](naming-guidelines.md)
