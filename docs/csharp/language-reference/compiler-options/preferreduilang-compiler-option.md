---
title: /preferreduilang (Opciones del compilador de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /preferreduilang
dev_langs:
- CSharp
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: 0fd8ccca016b598b14780ac6cd2190442777fb53
ms.contentlocale: es-es
ms.lasthandoff: 03/24/2017

---
# <a name="preferreduilang-c-compiler-options"></a>/preferreduilang (Opciones del compilador de C#)
Mediante la opción del compilador `/preferreduilang`, puede especificar el idioma en el que el compilador de C# muestra el resultado, como los mensajes de error.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/preferreduilang: language  
```  
  
## <a name="arguments"></a>Argumentos  
 `language`  
 El [nombre del idioma](http://go.microsoft.com/fwlink/p/?LinkId=236992) del idioma que se va a usar para los resultados del compilador.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar la opción del compilador `/preferreduilang` para especificar el idioma que quiere que use el compilador de C# para los mensajes de error y otros resultados de la línea de comandos. Si el paquete de idioma para el idioma no está instalado, se usa la configuración del idioma del sistema operativo en su lugar, y no se notifica ningún error.  
  
```csharp  
csc.exe /preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a>Requisitos  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)
