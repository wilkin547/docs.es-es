---
title: -baseaddress
ms.date: 08/09/2018
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
ms.openlocfilehash: 6ee842dbe65cbd9d147e77ec523a2b031d303738
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002391"
---
# <a name="-baseaddress"></a>-baseaddress
Especifica una dirección base predeterminada al crear un archivo DLL.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`address`|Obligatorio. La dirección base del archivo DLL. Esta dirección debe especificarse como un número hexadecimal.|  
  
## <a name="remarks"></a>Comentarios  
 La dirección base predeterminada para un archivo DLL se establece mediante el .NET Framework.  
  
 Tenga en cuenta que la palabra de orden inferior de esta dirección se redondea. Por ejemplo, si especifica 0x11110001, se redondea a 0x11110000.  
  
 Para completar el proceso de firma de un archivo DLL, use la opción `–R` de la herramienta de nombres seguros (SN. exe).  
  
 Esta opción se omite si el destino no es un archivo DLL.  
  
|Para Set-BaseAddress en el IDE de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Haga clic en **Avanzado**.<br />4.  Modifique el valor en el cuadro **dirección base del archivo dll:** . **Nota:**      El cuadro **dirección base del archivo dll:** es de solo lectura, a menos que el destino sea un archivo dll.|  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [SN. exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md))
