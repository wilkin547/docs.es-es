---
title: 'Cómo: Usar caracteres especiales en XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: 59449637bb45f6b75462b6809c354af7972fc2e7
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740833"
---
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="f4a11-102">Cómo: Usar caracteres especiales en XAML</span><span class="sxs-lookup"><span data-stu-id="f4a11-102">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="f4a11-103">Los archivos de marcado que se crean en Visual Studio se guardan automáticamente en el formato de archivo Unicode UTF-8, lo que significa que la mayoría de los caracteres especiales, como las marcas de acento, se codifican correctamente.</span><span class="sxs-lookup"><span data-stu-id="f4a11-103">Markup files that are created in Visual Studio are automatically saved in the Unicode UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="f4a11-104">Sin embargo, hay un conjunto de caracteres especiales usados que se controlan de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="f4a11-104">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="f4a11-105">Estos caracteres especiales siguen el estándar XML de World Wide Web Consortium (W3C) para la codificación.</span><span class="sxs-lookup"><span data-stu-id="f4a11-105">These special characters follow the World Wide Web Consortium (W3C) XML standard for encoding.</span></span>  
  
 <span data-ttu-id="f4a11-106">En la tabla siguiente se muestra la sintaxis para codificar este conjunto de caracteres especiales:</span><span class="sxs-lookup"><span data-stu-id="f4a11-106">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="f4a11-107">Carácter</span><span class="sxs-lookup"><span data-stu-id="f4a11-107">Character</span></span>|<span data-ttu-id="f4a11-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4a11-108">Syntax</span></span>|<span data-ttu-id="f4a11-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4a11-109">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`&lt;`|<span data-ttu-id="f4a11-110">Símbolo Menor que.</span><span class="sxs-lookup"><span data-stu-id="f4a11-110">Less than symbol.</span></span>|  
|>|`&gt;`|<span data-ttu-id="f4a11-111">Símbolo Mayor que.</span><span class="sxs-lookup"><span data-stu-id="f4a11-111">Greater than sign.</span></span>|  
|&|`&amp;`|<span data-ttu-id="f4a11-112">Símbolo Y comercial.</span><span class="sxs-lookup"><span data-stu-id="f4a11-112">Ampersand symbol.</span></span>|  
|<span data-ttu-id="f4a11-113">"</span><span class="sxs-lookup"><span data-stu-id="f4a11-113">"</span></span>|`&quot;`|<span data-ttu-id="f4a11-114">Símbolo Comilla doble.</span><span class="sxs-lookup"><span data-stu-id="f4a11-114">Double quote symbol.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="f4a11-115">Si crea un archivo de marcado mediante un editor de texto, como el Bloc de notas de Windows, debe guardar el archivo en el formato de archivo UTF-8 de Unicode para conservar los caracteres especiales codificados.</span><span class="sxs-lookup"><span data-stu-id="f4a11-115">If you create a markup file using a text editor, such as Windows Notepad, you must save the file in the Unicode UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="f4a11-116">En el ejemplo siguiente, se muestra cómo usar caracteres especiales en texto cuando se crea la marcación.</span><span class="sxs-lookup"><span data-stu-id="f4a11-116">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4a11-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f4a11-117">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
