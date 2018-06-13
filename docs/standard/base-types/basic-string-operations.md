---
title: Operaciones básicas de cadenas en .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- strings [.NET Framework], basic string operations
- custom strings
ms.assetid: 8133d357-90b5-4b62-9927-43323d99b6b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f7692251a00c712f93b649d4cd6fc153bb248f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33567489"
---
# <a name="basic-string-operations-in-net"></a><span data-ttu-id="48434-102">Operaciones básicas de cadenas en .NET</span><span class="sxs-lookup"><span data-stu-id="48434-102">Basic String Operations in .NET</span></span>
<span data-ttu-id="48434-103">A menudo, las aplicaciones responden a los usuarios mediante la construcción de mensajes basados en los datos proporcionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="48434-103">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="48434-104">Por ejemplo, no es raro que los sitios web respondan a un usuario que acaba de iniciar sesión con un saludo especializado que incluye el nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="48434-104">For example, it is not uncommon for Web sites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span> <span data-ttu-id="48434-105">Varios métodos de las clases <xref:System.String?displayProperty=nameWithType> y <xref:System.Text.StringBuilder?displayProperty=nameWithType> le permiten construir cadenas personalizadas de forma dinámica para mostrarlas en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="48434-105">Several methods in the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="48434-106">Estos métodos también le ayudan a realizar una serie de operaciones básicas de cadenas, como crear cadenas nuevas a partir de matrices de bytes, comparar los valores de cadenas y modificar cadenas existentes.</span><span class="sxs-lookup"><span data-stu-id="48434-106">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="48434-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="48434-107">In This Section</span></span>  
 [<span data-ttu-id="48434-108">Creación de cadenas nuevas</span><span class="sxs-lookup"><span data-stu-id="48434-108">Creating New Strings</span></span>](../../../docs/standard/base-types/creating-new.md)  
 <span data-ttu-id="48434-109">Se describen formas básicas para convertir objetos en cadenas y combinar cadenas.</span><span class="sxs-lookup"><span data-stu-id="48434-109">Describes basic ways to convert objects into strings and to combine strings.</span></span>  
  
 [<span data-ttu-id="48434-110">Recortar y quitar caracteres</span><span class="sxs-lookup"><span data-stu-id="48434-110">Trimming and Removing Characters</span></span>](../../../docs/standard/base-types/trimming.md)  
 <span data-ttu-id="48434-111">Se describe cómo recortar o quitar caracteres de una cadena.</span><span class="sxs-lookup"><span data-stu-id="48434-111">Describes how to trim or remove characters in a string.</span></span>  
  
 [<span data-ttu-id="48434-112">Rellenado de cadenas</span><span class="sxs-lookup"><span data-stu-id="48434-112">Padding Strings</span></span>](../../../docs/standard/base-types/padding.md)  
 <span data-ttu-id="48434-113">Describe cómo insertar caracteres o espacios vacíos en una cadena.</span><span class="sxs-lookup"><span data-stu-id="48434-113">Describes how to insert characters or empty spaces into a string.</span></span>  
  
 [<span data-ttu-id="48434-114">Comparar cadenas</span><span class="sxs-lookup"><span data-stu-id="48434-114">Comparing Strings</span></span>](../../../docs/standard/base-types/comparing.md)  
 <span data-ttu-id="48434-115">Se describe cómo comparar el contenido de dos o más cadenas.</span><span class="sxs-lookup"><span data-stu-id="48434-115">Describes how to compare the contents of two or more strings.</span></span>  
  
 [<span data-ttu-id="48434-116">Cambio de mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="48434-116">Changing Case</span></span>](../../../docs/standard/base-types/changing-case.md)  
 <span data-ttu-id="48434-117">Se describe cómo cambiar las mayúsculas y minúsculas de los caracteres de una cadena.</span><span class="sxs-lookup"><span data-stu-id="48434-117">Describes how to change the case of characters within a string.</span></span>  
  
 [<span data-ttu-id="48434-118">Utilizar la clase StringBuilder</span><span class="sxs-lookup"><span data-stu-id="48434-118">Using the StringBuilder Class</span></span>](../../../docs/standard/base-types/stringbuilder.md)  
 <span data-ttu-id="48434-119">Se describe cómo crear y modificar objetos de cadena dinámicos con la clase <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="48434-119">Describes how to create and modify dynamic string objects with the <xref:System.Text.StringBuilder> class.</span></span>  
  
 [<span data-ttu-id="48434-120">Realizar manipulaciones de cadena básicas</span><span class="sxs-lookup"><span data-stu-id="48434-120">How to: Perform Basic String Manipulations</span></span>](../../../docs/standard/base-types/basic-manipulations.md)  
 <span data-ttu-id="48434-121">Se describe el uso de las operaciones de cadena básicas.</span><span class="sxs-lookup"><span data-stu-id="48434-121">Demonstrates the use of basic string operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="48434-122">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="48434-122">Related Sections</span></span>  
 [<span data-ttu-id="48434-123">Conversión de tipos en .NET</span><span class="sxs-lookup"><span data-stu-id="48434-123">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="48434-124">Se describe cómo convertir un tipo en otro.</span><span class="sxs-lookup"><span data-stu-id="48434-124">Describes how to convert one type into another type.</span></span>  
  
 [<span data-ttu-id="48434-125">Aplicación de formato a tipos</span><span class="sxs-lookup"><span data-stu-id="48434-125">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="48434-126">Se describe cómo dar formato a cadenas mediante los especificadores de formato.</span><span class="sxs-lookup"><span data-stu-id="48434-126">Describes how to format strings using format specifiers.</span></span>
