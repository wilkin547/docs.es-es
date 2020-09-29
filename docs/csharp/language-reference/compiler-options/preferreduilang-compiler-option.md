---
description: -preferreduilang (Opciones del compilador de C#)
title: -preferreduilang (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
ms.openlocfilehash: 490f5926fb50cfdae740b7749d72ea6c9a1f8cc9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193821"
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="9c2ff-103">-preferreduilang (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="9c2ff-103">-preferreduilang (C# Compiler Options)</span></span>

<span data-ttu-id="9c2ff-104">Mediante la opción del compilador `-preferreduilang`, puede especificar el idioma en el que el compilador de C# muestra el resultado, como los mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="9c2ff-104">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c2ff-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c2ff-105">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="9c2ff-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9c2ff-106">Arguments</span></span>  

 `language`  
 <span data-ttu-id="9c2ff-107">El [nombre del idioma](/windows/desktop/Intl/language-names) del idioma que se va a usar para los resultados del compilador.</span><span class="sxs-lookup"><span data-stu-id="9c2ff-107">The [language name](/windows/desktop/Intl/language-names) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c2ff-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9c2ff-108">Remarks</span></span>  

 <span data-ttu-id="9c2ff-109">Puede usar la opción del compilador `-preferreduilang` para especificar el idioma que quiere que use el compilador de C# para los mensajes de error y otros resultados de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="9c2ff-109">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="9c2ff-110">Si el paquete de idioma para el idioma no está instalado, se usa la configuración del idioma del sistema operativo en su lugar, y no se notifica ningún error.</span><span class="sxs-lookup"><span data-stu-id="9c2ff-110">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="9c2ff-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c2ff-111">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c2ff-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c2ff-112">See also</span></span>

- [<span data-ttu-id="9c2ff-113">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="9c2ff-113">C# Compiler Options</span></span>](./index.md)
