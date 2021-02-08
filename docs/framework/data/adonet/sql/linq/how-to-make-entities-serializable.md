---
description: 'Más información sobre: Cómo: hacer que las entidades sean serializables'
title: Procedimiento para serializar entidades
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: cb2253d7933f3584543b4b030bc8b5aa3cc62921
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785944"
---
# <a name="how-to-make-entities-serializable"></a><span data-ttu-id="d3703-103">Procedimiento para serializar entidades</span><span class="sxs-lookup"><span data-stu-id="d3703-103">How to: Make Entities Serializable</span></span>

<span data-ttu-id="d3703-104">Puede hacer que las entidades sean serializables al generar el código.</span><span class="sxs-lookup"><span data-stu-id="d3703-104">You can make entities serializable when you generate your code.</span></span> <span data-ttu-id="d3703-105">Las clases de entidad se decoran con el atributo <xref:System.Runtime.Serialization.DataContractAttribute> y las columnas con el atributo <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d3703-105">Entity classes are decorated with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute, and columns with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="d3703-106">Los desarrolladores que usan Visual Studio pueden usar el Object Relational Designer para este fin.</span><span class="sxs-lookup"><span data-stu-id="d3703-106">Developers using Visual Studio can use the Object Relational Designer for this purpose.</span></span>  
  
 <span data-ttu-id="d3703-107">Si usa la herramienta de línea de comandos de SQLMetal, use la opción **/Serialization** con el `unidirectional` argumento.</span><span class="sxs-lookup"><span data-stu-id="d3703-107">If you are using the SQLMetal command-line tool, use the **/serialization** option with the `unidirectional` argument.</span></span> <span data-ttu-id="d3703-108">Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="d3703-108">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3703-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d3703-109">Example</span></span>  

 <span data-ttu-id="d3703-110">Con las siguientes líneas de comandos de SQLMetal se generan archivos que tienen entidades serializables.</span><span class="sxs-lookup"><span data-stu-id="d3703-110">The following SQLMetal command lines produce files that have serializable entities.</span></span>  
  
```console  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```console  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3703-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3703-111">See also</span></span>

- [<span data-ttu-id="d3703-112">Serialización</span><span class="sxs-lookup"><span data-stu-id="d3703-112">Serialization</span></span>](serialization.md)
- [<span data-ttu-id="d3703-113">Crear el modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="d3703-113">Creating the Object Model</span></span>](creating-the-object-model.md)
