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
ms.openlocfilehash: ccf25e9a5d5d025f9024519b41c4afa17a5081f4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="preferreduilang-c-compiler-options"></a>/preferreduilang (Opciones del compilador de C#)
Mediante la opción del compilador `/preferreduilang`, puede especificar el idioma en el que el compilador de C# muestra el resultado, como los mensajes de error.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
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
