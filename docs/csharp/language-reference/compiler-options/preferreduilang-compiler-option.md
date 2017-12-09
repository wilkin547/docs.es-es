---
title: -preferreduilang (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a96a054b3d1f73b0fee209557388f7ea213ebbe9
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="preferreduilang-c-compiler-options"></a><span data-ttu-id="067dd-102">/preferreduilang (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="067dd-102">/preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="067dd-103">Mediante la opción del compilador `/preferreduilang`, puede especificar el idioma en el que el compilador de C# muestra el resultado, como los mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="067dd-103">By using the `/preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="067dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="067dd-104">Syntax</span></span>  
  
```console  
/preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="067dd-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="067dd-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="067dd-106">El [nombre del idioma](https://msdn.microsoft.com/library/windows/desktop/dd318696(v=vs.85).aspx) del idioma que se va a usar para los resultados del compilador.</span><span class="sxs-lookup"><span data-stu-id="067dd-106">The [language name](https://msdn.microsoft.com/library/windows/desktop/dd318696(v=vs.85).aspx) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="067dd-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="067dd-107">Remarks</span></span>  
 <span data-ttu-id="067dd-108">Puede usar la opción del compilador `/preferreduilang` para especificar el idioma que quiere que use el compilador de C# para los mensajes de error y otros resultados de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="067dd-108">You can use the `/preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="067dd-109">Si el paquete de idioma para el idioma no está instalado, se usa la configuración del idioma del sistema operativo en su lugar, y no se notifica ningún error.</span><span class="sxs-lookup"><span data-stu-id="067dd-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe /preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="067dd-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="067dd-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="067dd-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="067dd-111">See Also</span></span>  
 [<span data-ttu-id="067dd-112">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="067dd-112">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
