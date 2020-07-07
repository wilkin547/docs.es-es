---
title: Procedimiento para generar ensamblados de interoperabilidad a partir de bibliotecas de tipos
description: Genere ensamblados de interoperabilidad a partir de bibliotecas de tipos. Use el importador de la biblioteca de tipos (Tlbimp.exe) para convertir coclases e interfaces de una biblioteca de tipos COM en metadatos.
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
ms.openlocfilehash: 6f54875d6aadb1da18cf25a1bec0a0e451f4a24c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619564"
---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a>Procedimiento para generar ensamblados de interoperabilidad a partir de bibliotecas de tipos
El [importador de la biblioteca de tipos (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) es una herramienta de línea de comandos que convierte las coclases e interfaces contenidas en una biblioteca de tipos COM en metadatos. Esta herramienta crea automáticamente un ensamblado de interoperabilidad y un espacio de nombres para la información de tipos. Una vez que los metadatos de una clase están disponibles, los clientes administrados pueden crear instancias del tipo COM y llamar a sus métodos, como si se tratara de una instancia de .NET. Tlbimp.exe convierte una biblioteca de tipos completa en metadatos de una vez y no se puede generar información de tipos para un subconjunto de los tipos definidos en una biblioteca de tipos.  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a>Para generar un ensamblado de interoperabilidad a partir de una biblioteca de tipos  
  
1. Use el siguiente comando:  
  
     **tlbimp** \<*type-library-file*>  
  
     Agregar el modificador **/out:** genera un ensamblado de interoperabilidad con un nombre modificado, como LOANLib.dll. Modificar el nombre de ensamblado de interoperabilidad puede ayudar a distinguirlo del archivo DLL original de COM e impedir problemas que pueden producirse al tener nombres duplicados.  
  
## <a name="example"></a>Ejemplo  
 El comando siguiente genera el ensamblado Loanlib.dll en el espacio de nombres `Loanlib`.  
  
```console  
tlbimp Loanlib.tlb  
```  
  
 El comando siguiente genera un ensamblado de interoperabilidad con un nombre modificado (LOANLib.dll).  
  
```console  
tlbimp LoanLib.tlb /out: LOANLib.dll  
```  
  
## <a name="see-also"></a>Vea también

- [Importar una biblioteca de tipos como un ensamblado](importing-a-type-library-as-an-assembly.md)
- [Exponer componentes COM en .NET Framework](exposing-com-components.md)
