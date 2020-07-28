---
title: 'Cómo: Usar caracteres especiales en XAML'
description: Obtenga información sobre la sintaxis para codificar caracteres especiales en el formato de archivo UTF-8 de Unicode en Visual Studio para su uso en archivos XAML en Windows Presentation Foundation.
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: ac2388fd96aa26ddd99408ac9f847ce517958568
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168353"
---
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="ced78-103">Cómo: Usar caracteres especiales en XAML</span><span class="sxs-lookup"><span data-stu-id="ced78-103">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="ced78-104">Los archivos de marcado que se crean en Visual Studio se guardan automáticamente en el formato de archivo Unicode UTF-8, lo que significa que la mayoría de los caracteres especiales, como las marcas de acento, se codifican correctamente.</span><span class="sxs-lookup"><span data-stu-id="ced78-104">Markup files that are created in Visual Studio are automatically saved in the Unicode UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="ced78-105">Sin embargo, hay un conjunto de caracteres especiales usados que se controlan de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="ced78-105">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="ced78-106">Estos caracteres especiales siguen el estándar XML de World Wide Web Consortium (W3C) para la codificación.</span><span class="sxs-lookup"><span data-stu-id="ced78-106">These special characters follow the World Wide Web Consortium (W3C) XML standard for encoding.</span></span>  
  
 <span data-ttu-id="ced78-107">En la tabla siguiente se muestra la sintaxis para codificar este conjunto de caracteres especiales:</span><span class="sxs-lookup"><span data-stu-id="ced78-107">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="ced78-108">Carácter</span><span class="sxs-lookup"><span data-stu-id="ced78-108">Character</span></span>|<span data-ttu-id="ced78-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ced78-109">Syntax</span></span>|<span data-ttu-id="ced78-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ced78-110">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`&lt;`|<span data-ttu-id="ced78-111">Símbolo Menor que.</span><span class="sxs-lookup"><span data-stu-id="ced78-111">Less than symbol.</span></span>|  
|>|`&gt;`|<span data-ttu-id="ced78-112">Símbolo Mayor que.</span><span class="sxs-lookup"><span data-stu-id="ced78-112">Greater than sign.</span></span>|  
|&|`&amp;`|<span data-ttu-id="ced78-113">Símbolo Y comercial.</span><span class="sxs-lookup"><span data-stu-id="ced78-113">Ampersand symbol.</span></span>|  
|<span data-ttu-id="ced78-114">"</span><span class="sxs-lookup"><span data-stu-id="ced78-114">"</span></span>|`&quot;`|<span data-ttu-id="ced78-115">Símbolo Comilla doble.</span><span class="sxs-lookup"><span data-stu-id="ced78-115">Double quote symbol.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="ced78-116">Si crea un archivo de marcado mediante un editor de texto, como el Bloc de notas de Windows, debe guardar el archivo en el formato de archivo UTF-8 de Unicode para conservar los caracteres especiales codificados.</span><span class="sxs-lookup"><span data-stu-id="ced78-116">If you create a markup file using a text editor, such as Windows Notepad, you must save the file in the Unicode UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="ced78-117">En el ejemplo siguiente, se muestra cómo usar caracteres especiales en texto cuando se crea la marcación.</span><span class="sxs-lookup"><span data-stu-id="ced78-117">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ced78-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ced78-118">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
