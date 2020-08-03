---
title: Procedimiento para controlar el tipo de una proyección (C#)
description: Obtenga información sobre cómo controlar el tipo de una proyección en LINQ en C# para crear colecciones de tipos que no sean IEnumerable<T> de XElement.
ms.date: 07/20/2015
ms.assetid: e4db6b7e-4cc9-4c8f-af85-94acf32aa348
ms.openlocfilehash: 32b019b5e1574e7160b4dce5fb0322caa3c1ca71
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103349"
---
# <a name="how-to-control-the-type-of-a-projection-c"></a><span data-ttu-id="745b9-103">Procedimiento para controlar el tipo de una proyección (C#)</span><span class="sxs-lookup"><span data-stu-id="745b9-103">How to control the type of a projection (C#)</span></span>
<span data-ttu-id="745b9-104">La proyección es el proceso de tomar un conjunto de datos, filtrarlo, cambiar su forma e incluso cambiar su tipo.</span><span class="sxs-lookup"><span data-stu-id="745b9-104">Projection is the process of taking one set of data, filtering it, changing its shape, and even changing its type.</span></span> <span data-ttu-id="745b9-105">La mayoría de las expresiones de consulta realizan proyecciones.</span><span class="sxs-lookup"><span data-stu-id="745b9-105">Most query expressions perform projections.</span></span> <span data-ttu-id="745b9-106">La mayor parte de las expresiones de consulta de esta sección se evalúan como <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement>, aunque puede controlar el tipo de proyección para crear colecciones de otros tipos.</span><span class="sxs-lookup"><span data-stu-id="745b9-106">Most of the query expressions shown in this section evaluate to <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, but you can control the type of the projection to create collections of other types.</span></span> <span data-ttu-id="745b9-107">En este tema se explica cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="745b9-107">This topic shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="745b9-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="745b9-108">Example</span></span>  
 <span data-ttu-id="745b9-109">En el ejemplo siguiente, se define un nuevo tipo, `Customer`.</span><span class="sxs-lookup"><span data-stu-id="745b9-109">The following example defines a new type, `Customer`.</span></span> <span data-ttu-id="745b9-110">La expresión de consulta crea una instancia de nuevos objetos `Customer` en la cláusula `Select`.</span><span class="sxs-lookup"><span data-stu-id="745b9-110">The query expression then instantiates new `Customer` objects in the `Select` clause.</span></span> <span data-ttu-id="745b9-111">Esto hace que el tipo de la expresión de consulta sea <xref:System.Collections.Generic.IEnumerable%601> de `Customer`.</span><span class="sxs-lookup"><span data-stu-id="745b9-111">This causes the type of the query expression to be <xref:System.Collections.Generic.IEnumerable%601> of `Customer`.</span></span>  
  
 <span data-ttu-id="745b9-112">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Clientes y pedidos (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="745b9-112">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
public class Customer  
{  
    private string customerID;  
    public string CustomerID{ get{return customerID;} set{customerID = value;}}  
  
    private string companyName;  
    public string CompanyName{ get{return companyName;} set{companyName = value;}}  
  
    private string contactName;  
    public string ContactName { get{return contactName;} set{contactName = value;}}  
  
    public Customer(string customerID, string companyName, string contactName)  
    {  
        CustomerID = customerID;  
        CompanyName = companyName;  
        ContactName = contactName;  
    }  
  
    public override string ToString()  
    {  
        return $"{this.customerID}:{this.companyName}:{this.contactName}";
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        XElement custOrd = XElement.Load("CustomersOrders.xml");  
        IEnumerable<Customer> custList =  
            from el in custOrd.Element("Customers").Elements("Customer")  
            select new Customer(  
                (string)el.Attribute("CustomerID"),  
                (string)el.Element("CompanyName"),  
                (string)el.Element("ContactName")  
            );  
        foreach (Customer cust in custList)  
            Console.WriteLine(cust);  
    }  
}  
```  
  
 <span data-ttu-id="745b9-113">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="745b9-113">This code produces the following output:</span></span>  
  
```output  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  
## <a name="see-also"></a><span data-ttu-id="745b9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="745b9-114">See also</span></span>

- <xref:System.Linq.Enumerable.Select%2A>
