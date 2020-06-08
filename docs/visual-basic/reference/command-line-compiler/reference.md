---
title: -reference
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
ms.openlocfilehash: 633b457106203e213f5d30003e576b7e8132f4d2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400492"
---
# <a name="-reference-visual-basic"></a>-reference (Visual Basic)
Hace que el compilador facilite al proyecto que se está compilando información de tipos en los ensamblados especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-reference:fileList  
```

o

```console
-r:fileList  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`fileList`|Obligatorio. Lista delimitada por comas de nombres de archivos de ensamblado. Si el nombre de archivo contiene un espacio, escríbalo entre comillas.|  
  
## <a name="remarks"></a>Comentarios  
 Los archivos que importe deben contener metadatos de ensamblado. Solo los tipos públicos son visibles fuera del ensamblado. La opción [-addmodule](addmodule.md) importa metadatos de un módulo.  
  
 Si hace referencia a un ensamblado (ensamblado A) que a su vez hace referencia a otro ensamblado (ensamblado B), debe hacer referencia al ensamblado B si:  
  
- Un tipo del ensamblado A hereda de un tipo o implementa una interfaz del ensamblado B.  
  
- Se invoca a un campo, una propiedad, un evento o un método que tiene un tipo de parámetro o un tipo de valor devuelto del ensamblado B.  
  
 Use [-libpath](libpath.md) para especificar el directorio en el que se encuentran una o varias de las referencias de ensamblado.  
  
 Para que el compilador reconozca un tipo en un ensamblado (no un módulo), se debe forzar la resolución del tipo. Un ejemplo de cómo puede hacerse es definir una instancia del tipo. Existen otras formas de resolver nombres de tipo en un ensamblado para el compilador. Por ejemplo, si se hereda de un tipo de un ensamblado, nombre del tipo pasa a ser conocido para el compilador.  
  
 De forma predeterminada se usa el archivo de respuesta Vbc.rsp, que hace referencia a los ensamblados de .NET Framework usados habitualmente. Use `-noconfig` si no quiere que el compilador use Vbc.rsp.  
  
 La forma abreviada de `-reference` es `-r`.  
  
## <a name="example"></a>Ejemplo  
 El comando siguiente compila el archivo de código fuente `Input.vb` y hace referencia a ensamblados de `Metad1.dll` y `Metad2.dll` para generar `Out.exe`.  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [-noconfig](noconfig.md)
- [-target (Visual Basic)](target.md)
- [Public](../../language-reference/modifiers/public.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
