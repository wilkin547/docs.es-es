---
title: -utf8output (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /utf8output
helpviewer_keywords:
- utf8output compiler option [C#]
- /utf8output compiler option [C#]
- -utf8output compiler option [C#]
ms.assetid: 27ff7381-c281-45d7-b2eb-1ad644b1354e
caps.latest.revision: "10"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3716445cb779e98f777a1677ff67e1ba603c5fa2
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="-utf8output-c-compiler-options"></a><span data-ttu-id="e8fd8-102">-utf8output (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="e8fd8-102">-utf8output (C# Compiler Options)</span></span>
<span data-ttu-id="e8fd8-103">La opción **-utf8output** muestra los resultados del compilador en codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="e8fd8-103">The **-utf8output** option displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8fd8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8fd8-104">Syntax</span></span>  
  
```console  
-utf8output  
```  
  
## <a name="remarks"></a><span data-ttu-id="e8fd8-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e8fd8-105">Remarks</span></span>  
 <span data-ttu-id="e8fd8-106">En algunas configuraciones internacionales, el resultado del compilador no puede mostrarse correctamente en la consola.</span><span class="sxs-lookup"><span data-stu-id="e8fd8-106">In some international configurations, compiler output cannot correctly be displayed in the console.</span></span> <span data-ttu-id="e8fd8-107">En estas configuraciones, use **-utf8output** y redirija el resultado del compilador a un archivo.</span><span class="sxs-lookup"><span data-stu-id="e8fd8-107">In these configurations, use **-utf8output** and redirect compiler output to a file.</span></span>  
  
 <span data-ttu-id="e8fd8-108">Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="e8fd8-108">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8fd8-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8fd8-109">See Also</span></span>  
 [<span data-ttu-id="e8fd8-110">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="e8fd8-110">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
