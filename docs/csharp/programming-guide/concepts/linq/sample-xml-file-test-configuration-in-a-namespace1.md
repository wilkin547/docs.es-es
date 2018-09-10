---
title: 'Archivo XML de ejemplo: Configuración de prueba en un espacio de nombres'
ms.date: 07/20/2015
ms.assetid: e75ad1bc-5636-4623-9a34-a286a8c485d6
ms.openlocfilehash: 01470a66ac42eb9fd68fdcde0d0a4bf9150e3d5f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506506"
---
# <a name="sample-xml-file-test-configuration-in-a-namespace"></a><span data-ttu-id="3c285-102">Archivo XML de ejemplo: Configuración de prueba en un espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="3c285-102">Sample XML File: Test Configuration in a Namespace</span></span>
<span data-ttu-id="3c285-103">El siguiente archivo XML se usa en numerosos ejemplos de la documentación de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c285-103">The following XML file is used in various examples in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] documentation.</span></span> <span data-ttu-id="3c285-104">Se trata de un archivo de configuración de pruebas.</span><span class="sxs-lookup"><span data-stu-id="3c285-104">This is a test configuration file.</span></span> <span data-ttu-id="3c285-105">El XML se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3c285-105">The XML is in a namespace.</span></span>  
  
## <a name="testconfiginnamespacexml"></a><span data-ttu-id="3c285-106">TestConfigInNamespace.xml</span><span class="sxs-lookup"><span data-stu-id="3c285-106">TestConfigInNamespace.xml</span></span>  
  
```xml  
<?xml version="1.0"?>  
<Tests xmlns="http://www.adatum.com">  
  <Test TestId="0001" TestType="CMD">  
    <Name>Convert number to string</Name>  
    <CommandLine>Examp1.EXE</CommandLine>  
    <Input>1</Input>  
    <Output>One</Output>  
  </Test>  
  <Test TestId="0002" TestType="CMD">  
    <Name>Find succeeding characters</Name>  
    <CommandLine>Examp2.EXE</CommandLine>  
    <Input>abc</Input>  
    <Output>def</Output>  
  </Test>  
  <Test TestId="0003" TestType="GUI">  
    <Name>Convert multiple numbers to strings</Name>  
    <CommandLine>Examp2.EXE /Verbose</CommandLine>  
    <Input>123</Input>  
    <Output>One Two Three</Output>  
  </Test>  
  <Test TestId="0004" TestType="GUI">  
    <Name>Find correlated key</Name>  
    <CommandLine>Examp3.EXE</CommandLine>  
    <Input>a1</Input>  
    <Output>b1</Output>  
  </Test>  
  <Test TestId="0005" TestType="GUI">  
    <Name>Count characters</Name>  
    <CommandLine>FinalExamp.EXE</CommandLine>  
    <Input>This is a test</Input>  
    <Output>14</Output>  
  </Test>  
  <Test TestId="0006" TestType="GUI">  
    <Name>Another Test</Name>  
    <CommandLine>Examp2.EXE</CommandLine>  
    <Input>Test Input</Input>  
    <Output>10</Output>  
  </Test>  
</Tests>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c285-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c285-107">See Also</span></span>

- [<span data-ttu-id="3c285-108">Documentos XML de ejemplo (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="3c285-108">Sample XML Documents (LINQ to XML)</span></span>](../../../../csharp/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)
