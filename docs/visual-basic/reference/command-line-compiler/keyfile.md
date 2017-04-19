---
title: / keyfile | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c36eac96ac6302db0b567e8249af726c807c2c6c
ms.lasthandoff: 03/13/2017

---
# <a name="keyfile"></a>/keyfile
Especifica un archivo que contiene una clave o un par de claves que asigna un nombre seguro al ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/keyfile:file  
```  
  
## <a name="arguments"></a>Argumentos  
 `file`  
 Obligatorio. Archivo que contiene la clave. Si el nombre de archivo contiene un espacio, encierre el nombre entre comillas ("").  
  
## <a name="remarks"></a>Comentarios  
 El compilador inserta la clave pública en el manifiesto del ensamblado y firma después el ensamblado final con la clave privada. Para generar un archivo de clave, escriba `sn -k file` en la línea de comandos. Para obtener más información, vea [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).  
  
 Si se compila con `/target:module`, el nombre del archivo de claves se mantiene en el módulo y se incorpora en el ensamblado que se crea al compilar un ensamblado con [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 También puede pasar la información de cifrado al compilador con [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md). Utilice [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) si desea firmar parcialmente un ensamblado.  
  
 También puede especificar esta opción como un atributo personalizado (<xref:System.Reflection.AssemblyKeyFileAttribute>) en el código fuente de cualquier módulo de lenguaje intermedio de Microsoft.</xref:System.Reflection.AssemblyKeyFileAttribute>  
  
 En caso de ambos `/keyfile` y [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) se especifican (opción de línea de comandos o mediante un atributo personalizado) en la misma compilación, el compilador intenta utilizar primero el contenedor de claves. Si se realiza correctamente, el ensamblado se firma con la información en el contenedor de claves. Si el compilador no encuentra el contenedor de claves, prueba con el archivo especificado con `/keyfile`. Si se realiza correctamente, el ensamblado se firma con la información en el archivo de clave y la información de clave se instala en el contenedor de claves (similar a `sn -i`) para que en la siguiente compilación, el contenedor de claves será válido.  
  
 Tenga en cuenta que un archivo de clave podría contener sólo la clave pública.  
  
 Consulte [crear y utilizar ensamblados](https://msdn.microsoft.com/library/xwb8f617) para obtener más información sobre cómo firmar un ensamblado.  
  
> [!NOTE]
>  El `/keyfile` opción no está disponible en la [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] entorno de desarrollo; está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente compila el archivo de código fuente `Input.vb` y especifica un archivo de clave.  
  
```  
vbc /keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Ensamblados y caché Global de ensamblados](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
