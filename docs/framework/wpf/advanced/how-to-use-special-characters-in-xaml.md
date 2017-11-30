---
title: "Cómo: Usar caracteres especiales en XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 308b2152f98286ba532a15e5491b5d1a25aa66dd
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="c2599-102">Cómo: Usar caracteres especiales en XAML</span><span class="sxs-lookup"><span data-stu-id="c2599-102">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="c2599-103">Archivos de marcado que se crean en [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] se guardan automáticamente en el [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] formato de archivo UTF-8, lo que significa que la mayoría de caracteres especiales, como signos de acentuación se codifican correctamente.</span><span class="sxs-lookup"><span data-stu-id="c2599-103">Markup files that are created in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] are automatically saved in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="c2599-104">Sin embargo, hay un conjunto de caracteres especiales usados que se controlan de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="c2599-104">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="c2599-105">Estos caracteres especiales siguen la [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] estándar para la codificación.</span><span class="sxs-lookup"><span data-stu-id="c2599-105">These special characters follow the [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)][!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard for encoding.</span></span>  
  
 <span data-ttu-id="c2599-106">En la tabla siguiente se muestra la sintaxis para codificar este conjunto de caracteres especiales:</span><span class="sxs-lookup"><span data-stu-id="c2599-106">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="c2599-107">Carácter</span><span class="sxs-lookup"><span data-stu-id="c2599-107">Character</span></span>|<span data-ttu-id="c2599-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2599-108">Syntax</span></span>|<span data-ttu-id="c2599-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2599-109">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`<`|<span data-ttu-id="c2599-110">Símbolo Menor que.</span><span class="sxs-lookup"><span data-stu-id="c2599-110">Less than symbol.</span></span>|  
|>|`>`|<span data-ttu-id="c2599-111">Símbolo Mayor que.</span><span class="sxs-lookup"><span data-stu-id="c2599-111">Greater than sign.</span></span>|  
|&|`&`|<span data-ttu-id="c2599-112">Símbolo Y comercial.</span><span class="sxs-lookup"><span data-stu-id="c2599-112">Ampersand symbol.</span></span>|  
|<span data-ttu-id="c2599-113">"</span><span class="sxs-lookup"><span data-stu-id="c2599-113">"</span></span>|`"`|<span data-ttu-id="c2599-114">Símbolo Comilla doble.</span><span class="sxs-lookup"><span data-stu-id="c2599-114">Double quote symbol.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="c2599-115">Si crea un archivo de marcado mediante un texto de editor, como [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] el Bloc de notas, debe guardar el archivo en el [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] formato de archivo UTF-8 con el fin de conservar cualquier codifica caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="c2599-115">If you create a markup file using a text editor, such as [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Notepad, you must save the file in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="c2599-116">En el ejemplo siguiente, se muestra cómo usar caracteres especiales en texto cuando se crea la marcación.</span><span class="sxs-lookup"><span data-stu-id="c2599-116">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2599-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2599-117">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
