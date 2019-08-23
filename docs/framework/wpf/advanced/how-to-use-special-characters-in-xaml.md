---
title: Procedimiento Usar caracteres especiales en XAML
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: 61ee38319b2f0aa46690fb063f6ffe6612f993ad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918441"
---
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="2bad1-102">Procedimiento Usar caracteres especiales en XAML</span><span class="sxs-lookup"><span data-stu-id="2bad1-102">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="2bad1-103">Los archivos de marcado que se [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] crean en se guardan [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] automáticamente en el formato de archivo UTF-8, lo que significa que la mayoría de los caracteres especiales, como las marcas de acento, se codifican correctamente.</span><span class="sxs-lookup"><span data-stu-id="2bad1-103">Markup files that are created in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] are automatically saved in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="2bad1-104">Sin embargo, hay un conjunto de caracteres especiales usados que se controlan de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="2bad1-104">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="2bad1-105">Estos caracteres especiales siguen el [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] estándar de codificación.</span><span class="sxs-lookup"><span data-stu-id="2bad1-105">These special characters follow the [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard for encoding.</span></span>  
  
 <span data-ttu-id="2bad1-106">En la tabla siguiente se muestra la sintaxis para codificar este conjunto de caracteres especiales:</span><span class="sxs-lookup"><span data-stu-id="2bad1-106">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="2bad1-107">Carácter</span><span class="sxs-lookup"><span data-stu-id="2bad1-107">Character</span></span>|<span data-ttu-id="2bad1-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2bad1-108">Syntax</span></span>|<span data-ttu-id="2bad1-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2bad1-109">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`&lt;`|<span data-ttu-id="2bad1-110">Símbolo Menor que.</span><span class="sxs-lookup"><span data-stu-id="2bad1-110">Less than symbol.</span></span>|  
|>|`&gt;`|<span data-ttu-id="2bad1-111">Símbolo Mayor que.</span><span class="sxs-lookup"><span data-stu-id="2bad1-111">Greater than sign.</span></span>|  
|&|`&amp;`|<span data-ttu-id="2bad1-112">Símbolo Y comercial.</span><span class="sxs-lookup"><span data-stu-id="2bad1-112">Ampersand symbol.</span></span>|  
|<span data-ttu-id="2bad1-113">"</span><span class="sxs-lookup"><span data-stu-id="2bad1-113">"</span></span>|`&quot;`|<span data-ttu-id="2bad1-114">Símbolo Comilla doble.</span><span class="sxs-lookup"><span data-stu-id="2bad1-114">Double quote symbol.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="2bad1-115">Si crea un archivo de marcado mediante un editor de texto, como el Bloc de notas de Windows, debe guardar el [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] archivo en el formato de archivo UTF-8 para conservar los caracteres especiales codificados.</span><span class="sxs-lookup"><span data-stu-id="2bad1-115">If you create a markup file using a text editor, such as Windows Notepad, you must save the file in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="2bad1-116">En el ejemplo siguiente, se muestra cómo usar caracteres especiales en texto cuando se crea la marcación.</span><span class="sxs-lookup"><span data-stu-id="2bad1-116">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bad1-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2bad1-117">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
