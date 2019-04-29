---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: c13f34c23cad9c909c2c5bd3447f1a8fa53f9b4d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793970"
---
# <a name="-keyfile"></a>-keyfile
Especifica un archivo que contiene una clave o un par de claves que asigna un nombre seguro al ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
``` 
-keyfile:file  
```  
  
## <a name="arguments"></a>Argumentos  
 `file`  
 Obligatorio. Archivo que contiene la clave. Si el nombre de archivo contiene un espacio, escriba el nombre entre comillas ("").  
  
## <a name="remarks"></a>Comentarios  
 El compilador inserta la clave pública en el manifiesto del ensamblado y, a continuación, firma el ensamblado final con la clave privada. Para generar un archivo de claves, escriba `sn -k file` en la línea de comandos. Para obtener más información, consulte [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).  
  
 Si se compila con `-target:module`, se mantiene en el módulo y se incorpora al ensamblado que se crea al compilar un ensamblado con el nombre del archivo de clave [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 También puede pasar la información de cifrado al compilador con [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md). Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) para firmar el ensamblado de forma parcial.  
  
 También puede especificar esta opción como un atributo personalizado (<xref:System.Reflection.AssemblyKeyFileAttribute>) en el código fuente de cualquier módulo de lenguaje intermedio de Microsoft.  
  
 En caso de ambos `-keyfile` y [- keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) se especifican (mediante una opción de línea de comandos o mediante un atributo personalizado) en la misma compilación, el compilador intenta en primer lugar el contenedor de claves. Si lo consigue, el ensamblado se firma con la información del contenedor de claves. Si el compilador no encuentra el contenedor de claves, prueba con el archivo especificado con `-keyfile`. Si esto se realiza correctamente, el ensamblado está firmado con la información del archivo de claves y la información de clave se instala en el contenedor de claves (similar a `sn -i`) para que en la siguiente compilación, el contenedor de claves será válido.  
  
 Tenga en cuenta que un archivo de clave puede contener solo la clave pública.  
  
 Consulte [crear y utilizar ensamblados](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) para obtener más información sobre cómo firmar un ensamblado.  
  
> [!NOTE]
>  El `-keyfile` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente compila el archivo de código fuente `Input.vb` y especifica un archivo de clave.  
  
```console  
vbc -keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Ensamblados de .NET](../../../standard/assembly/index.md)
- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-referencia (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
