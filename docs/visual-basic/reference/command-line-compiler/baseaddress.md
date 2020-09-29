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
ms.openlocfilehash: c794d1fc1c9d20e22ffa747e3175c846341ad8ad
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097766"
---
# <a name="-baseaddress"></a>-baseaddress

Especifica una dirección base predeterminada al crear un archivo DLL.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`address`|Obligatorio. La dirección base del archivo DLL. Esta dirección debe especificarse como un número hexadecimal.|  
  
## <a name="remarks"></a>Comentarios  

 .NET Framework establece la dirección base predeterminada de un archivo DLL.  
  
 Tenga en cuenta que la palabra de orden inferior en esta dirección se redondea. Por ejemplo, si se especifica 0x11110001, se redondea a 0x11110000.  
  
 Para completar el proceso de firma de un archivo DLL, use la opción `–R` de la herramienta de nombre seguro (Sn.exe).  
  
 Esta opción se omite si el destino no es un archivo DLL.  
  
|Para establecer -baseaddress en el IDE de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Haga clic en **Avanzado**.<br />4.  Modifique el valor en el cuadro **Dirección base del archivo DLL**. **Nota:**      El cuadro **Dirección base del archivo DLL** es de solo lectura excepto si el destino es un archivo DLL.|  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [-target (Visual Basic)](target.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
- [Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md)
