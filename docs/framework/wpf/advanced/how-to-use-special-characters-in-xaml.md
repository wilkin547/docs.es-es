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
# <a name="how-to-use-special-characters-in-xaml"></a>Cómo: Usar caracteres especiales en XAML
Los archivos de marcado que se crean en Visual Studio se guardan automáticamente en el formato de archivo Unicode UTF-8, lo que significa que la mayoría de los caracteres especiales, como las marcas de acento, se codifican correctamente. Sin embargo, hay un conjunto de caracteres especiales usados que se controlan de forma diferente. Estos caracteres especiales siguen el estándar XML de World Wide Web Consortium (W3C) para la codificación.  
  
 En la tabla siguiente se muestra la sintaxis para codificar este conjunto de caracteres especiales:  
  
|Carácter|Sintaxis|Descripción|  
|---------------|------------|-----------------|  
|<|`&lt;`|Símbolo Menor que.|  
|>|`&gt;`|Símbolo Mayor que.|  
|&|`&amp;`|Símbolo Y comercial.|  
|"|`&quot;`|Símbolo Comilla doble.|  
  
> [!NOTE]
> Si crea un archivo de marcado mediante un editor de texto, como el Bloc de notas de Windows, debe guardar el archivo en el formato de archivo UTF-8 de Unicode para conservar los caracteres especiales codificados.  
  
 En el ejemplo siguiente, se muestra cómo usar caracteres especiales en texto cuando se crea la marcación.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
