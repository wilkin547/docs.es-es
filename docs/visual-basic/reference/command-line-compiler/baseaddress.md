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
ms.openlocfilehash: 6331a55bb1d20b5804605db103dcfd2997e348d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="-baseaddress"></a>-baseaddress
Especifica una dirección base predeterminada al crear un archivo DLL.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-baseaddress:address  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`address`|Requerido. La dirección base del archivo DLL. Esta dirección debe especificarse como un número hexadecimal.|  
  
## <a name="remarks"></a>Comentarios  
 La dirección base predeterminada para un archivo DLL se establece el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].  
  
 Tenga en cuenta que la palabra de orden inferior de esta dirección se redondea. Por ejemplo, si especifica 0 x 11110001, se redondea como 0 x 11110000.  
  
 Para completar el proceso de firma de un archivo DLL, utilice la `–R` opción de la herramienta de nombres seguros (Sn.exe).  
  
 Esta opción se omite si el destino no es un archivo DLL.  
  
|Para establecer - baseaddress en el IDE de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Haga clic en **Avanzado**.<br />4.  Modifique el valor en el **dirección base del archivo DLL:** cuadro. **Nota:** el **dirección base del archivo DLL:** cuadro es de solo lectura, a menos que el destino es un archivo DLL.|  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Sn.exe (herramienta de nombre seguro)] [Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md))
