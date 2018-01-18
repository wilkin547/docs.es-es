---
title: Colecciones de esquemas de OLE DB
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 33e794559abd7f619f7431683f06e59705b57d41
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="e6ce6-102">Colecciones de esquemas de OLE DB</span><span class="sxs-lookup"><span data-stu-id="e6ce6-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="e6ce6-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los proveedores OLE DB de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="e6ce6-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="e6ce6-104">Proveedor OLE DB para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="e6ce6-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="e6ce6-105">El controlador OLE DB de Microsoft SQL Server admite además las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="e6ce6-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="e6ce6-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="e6ce6-106">Tables</span></span>  
  
-   <span data-ttu-id="e6ce6-107">Columnas</span><span class="sxs-lookup"><span data-stu-id="e6ce6-107">Columns</span></span>  
  
-   <span data-ttu-id="e6ce6-108">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="e6ce6-108">Procedures</span></span>  
  
-   <span data-ttu-id="e6ce6-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e6ce6-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="e6ce6-110">Catálogo</span><span class="sxs-lookup"><span data-stu-id="e6ce6-110">Catalog</span></span>  
  
-   <span data-ttu-id="e6ce6-111">Índices</span><span class="sxs-lookup"><span data-stu-id="e6ce6-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="e6ce6-112">Tablas</span><span class="sxs-lookup"><span data-stu-id="e6ce6-112">Tables</span></span>  
  
|<span data-ttu-id="e6ce6-113">ColumName</span><span class="sxs-lookup"><span data-stu-id="e6ce6-113">ColumnName</span></span>|<span data-ttu-id="e6ce6-114">DataType</span><span class="sxs-lookup"><span data-stu-id="e6ce6-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e6ce6-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-115">TABLE_CATALOG</span></span>|<span data-ttu-id="e6ce6-116">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-116">String</span></span>|  
|<span data-ttu-id="e6ce6-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="e6ce6-118">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-118">String</span></span>|  
|<span data-ttu-id="e6ce6-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-119">TABLE_NAME</span></span>|<span data-ttu-id="e6ce6-120">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-120">String</span></span>|  
|<span data-ttu-id="e6ce6-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-121">TABLE_TYPE</span></span>|<span data-ttu-id="e6ce6-122">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-122">String</span></span>|  
|<span data-ttu-id="e6ce6-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-123">TABLE_GUID</span></span>|<span data-ttu-id="e6ce6-124">Guid</span><span class="sxs-lookup"><span data-stu-id="e6ce6-124">Guid</span></span>|  
|<span data-ttu-id="e6ce6-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-125">DESCRIPTION</span></span>|<span data-ttu-id="e6ce6-126">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-126">String</span></span>|  
|<span data-ttu-id="e6ce6-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-127">TABLE_PROPID</span></span>|<span data-ttu-id="e6ce6-128">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-128">Int64</span></span>|  
|<span data-ttu-id="e6ce6-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-129">DATE_CREATED</span></span>|<span data-ttu-id="e6ce6-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="e6ce6-130">DateTime</span></span>|  
|<span data-ttu-id="e6ce6-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-131">DATE_MODIFIED</span></span>|<span data-ttu-id="e6ce6-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="e6ce6-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e6ce6-133">Columnas</span><span class="sxs-lookup"><span data-stu-id="e6ce6-133">Columns</span></span>  
  
|<span data-ttu-id="e6ce6-134">ColumName</span><span class="sxs-lookup"><span data-stu-id="e6ce6-134">ColumnName</span></span>|<span data-ttu-id="e6ce6-135">DataType</span><span class="sxs-lookup"><span data-stu-id="e6ce6-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e6ce6-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-136">TABLE_CATALOG</span></span>|<span data-ttu-id="e6ce6-137">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-137">String</span></span>|  
|<span data-ttu-id="e6ce6-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="e6ce6-139">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-139">String</span></span>|  
|<span data-ttu-id="e6ce6-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-140">TABLE_NAME</span></span>|<span data-ttu-id="e6ce6-141">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-141">String</span></span>|  
|<span data-ttu-id="e6ce6-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-142">COLUMN_NAME</span></span>|<span data-ttu-id="e6ce6-143">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-143">String</span></span>|  
|<span data-ttu-id="e6ce6-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-144">COLUMN_GUID</span></span>|<span data-ttu-id="e6ce6-145">Guid</span><span class="sxs-lookup"><span data-stu-id="e6ce6-145">Guid</span></span>|  
|<span data-ttu-id="e6ce6-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-146">COLUMN_PROPID</span></span>|<span data-ttu-id="e6ce6-147">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-147">Int64</span></span>|  
|<span data-ttu-id="e6ce6-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="e6ce6-149">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-149">Int64</span></span>|  
|<span data-ttu-id="e6ce6-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="e6ce6-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="e6ce6-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-151">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e6ce6-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="e6ce6-153">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-153">String</span></span>|  
|<span data-ttu-id="e6ce6-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="e6ce6-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="e6ce6-155">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-155">Int64</span></span>|  
|<span data-ttu-id="e6ce6-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-156">IS_NULLABLE</span></span>|<span data-ttu-id="e6ce6-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-157">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-158">DATA_TYPE</span></span>|<span data-ttu-id="e6ce6-159">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-159">Int32</span></span>|  
|<span data-ttu-id="e6ce6-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-160">TYPE_GUID</span></span>|<span data-ttu-id="e6ce6-161">Guid</span><span class="sxs-lookup"><span data-stu-id="e6ce6-161">Guid</span></span>|  
|<span data-ttu-id="e6ce6-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e6ce6-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="e6ce6-163">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-163">Int64</span></span>|  
|<span data-ttu-id="e6ce6-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e6ce6-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="e6ce6-165">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-165">Int64</span></span>|  
|<span data-ttu-id="e6ce6-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="e6ce6-167">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-167">Int32</span></span>|  
|<span data-ttu-id="e6ce6-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="e6ce6-169">Int16</span><span class="sxs-lookup"><span data-stu-id="e6ce6-169">Int16</span></span>|  
|<span data-ttu-id="e6ce6-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="e6ce6-171">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-171">Int64</span></span>|  
|<span data-ttu-id="e6ce6-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="e6ce6-173">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-173">String</span></span>|  
|<span data-ttu-id="e6ce6-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="e6ce6-175">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-175">String</span></span>|  
|<span data-ttu-id="e6ce6-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="e6ce6-177">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-177">String</span></span>|  
|<span data-ttu-id="e6ce6-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="e6ce6-179">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-179">String</span></span>|  
|<span data-ttu-id="e6ce6-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="e6ce6-181">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-181">String</span></span>|  
|<span data-ttu-id="e6ce6-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-182">COLLATION_NAME</span></span>|<span data-ttu-id="e6ce6-183">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-183">String</span></span>|  
|<span data-ttu-id="e6ce6-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="e6ce6-185">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-185">String</span></span>|  
|<span data-ttu-id="e6ce6-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="e6ce6-187">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-187">String</span></span>|  
|<span data-ttu-id="e6ce6-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-188">DOMAIN_NAME</span></span>|<span data-ttu-id="e6ce6-189">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-189">String</span></span>|  
|<span data-ttu-id="e6ce6-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-190">DESCRIPTION</span></span>|<span data-ttu-id="e6ce6-191">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-191">String</span></span>|  
|<span data-ttu-id="e6ce6-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-192">COLUMN_LCID</span></span>|<span data-ttu-id="e6ce6-193">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-193">Int32</span></span>|  
|<span data-ttu-id="e6ce6-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="e6ce6-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="e6ce6-195">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-195">Int32</span></span>|  
|<span data-ttu-id="e6ce6-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-196">COLUMN_SORTID</span></span>|<span data-ttu-id="e6ce6-197">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-197">Int32</span></span>|  
|<span data-ttu-id="e6ce6-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="e6ce6-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="e6ce6-199">Byte[]</span></span>|  
|<span data-ttu-id="e6ce6-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-200">IS_COMPUTED</span></span>|<span data-ttu-id="e6ce6-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e6ce6-202">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="e6ce6-202">Procedures</span></span>  
  
|<span data-ttu-id="e6ce6-203">ColumName</span><span class="sxs-lookup"><span data-stu-id="e6ce6-203">ColumnName</span></span>|<span data-ttu-id="e6ce6-204">DataType</span><span class="sxs-lookup"><span data-stu-id="e6ce6-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e6ce6-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="e6ce6-206">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-206">String</span></span>|  
|<span data-ttu-id="e6ce6-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="e6ce6-208">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-208">String</span></span>|  
|<span data-ttu-id="e6ce6-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="e6ce6-210">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-210">String</span></span>|  
|<span data-ttu-id="e6ce6-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e6ce6-212">Int16</span><span class="sxs-lookup"><span data-stu-id="e6ce6-212">Int16</span></span>|  
|<span data-ttu-id="e6ce6-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="e6ce6-214">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-214">String</span></span>|  
|<span data-ttu-id="e6ce6-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-215">DESCRIPTION</span></span>|<span data-ttu-id="e6ce6-216">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-216">String</span></span>|  
|<span data-ttu-id="e6ce6-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-217">DATE_CREATED</span></span>|<span data-ttu-id="e6ce6-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="e6ce6-218">DateTime</span></span>|  
|<span data-ttu-id="e6ce6-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-219">DATE_MODIFIED</span></span>|<span data-ttu-id="e6ce6-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="e6ce6-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="e6ce6-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e6ce6-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="e6ce6-222">ColumName</span><span class="sxs-lookup"><span data-stu-id="e6ce6-222">ColumnName</span></span>|<span data-ttu-id="e6ce6-223">DataType</span><span class="sxs-lookup"><span data-stu-id="e6ce6-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e6ce6-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="e6ce6-225">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-225">String</span></span>|  
|<span data-ttu-id="e6ce6-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="e6ce6-227">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-227">String</span></span>|  
|<span data-ttu-id="e6ce6-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="e6ce6-229">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-229">String</span></span>|  
|<span data-ttu-id="e6ce6-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-230">PARAMETER_NAME</span></span>|<span data-ttu-id="e6ce6-231">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-231">String</span></span>|  
|<span data-ttu-id="e6ce6-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="e6ce6-233">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-233">Int32</span></span>|  
|<span data-ttu-id="e6ce6-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="e6ce6-235">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-235">Int32</span></span>|  
|<span data-ttu-id="e6ce6-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="e6ce6-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="e6ce6-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-237">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e6ce6-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="e6ce6-239">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-239">String</span></span>|  
|<span data-ttu-id="e6ce6-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-240">IS_NULLABLE</span></span>|<span data-ttu-id="e6ce6-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-241">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-242">DATA_TYPE</span></span>|<span data-ttu-id="e6ce6-243">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-243">Int32</span></span>|  
|<span data-ttu-id="e6ce6-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e6ce6-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="e6ce6-245">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-245">Int64</span></span>|  
|<span data-ttu-id="e6ce6-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e6ce6-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="e6ce6-247">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-247">Int64</span></span>|  
|<span data-ttu-id="e6ce6-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="e6ce6-249">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-249">Int32</span></span>|  
|<span data-ttu-id="e6ce6-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="e6ce6-251">Int16</span><span class="sxs-lookup"><span data-stu-id="e6ce6-251">Int16</span></span>|  
|<span data-ttu-id="e6ce6-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-252">DESCRIPTION</span></span>|<span data-ttu-id="e6ce6-253">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-253">String</span></span>|  
|<span data-ttu-id="e6ce6-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-254">TYPE_NAME</span></span>|<span data-ttu-id="e6ce6-255">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-255">String</span></span>|  
|<span data-ttu-id="e6ce6-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="e6ce6-257">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="e6ce6-258">Catálogo</span><span class="sxs-lookup"><span data-stu-id="e6ce6-258">Catalog</span></span>  
  
|<span data-ttu-id="e6ce6-259">ColumName</span><span class="sxs-lookup"><span data-stu-id="e6ce6-259">ColumnName</span></span>|<span data-ttu-id="e6ce6-260">DataType</span><span class="sxs-lookup"><span data-stu-id="e6ce6-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e6ce6-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-261">CATALOG_NAME</span></span>|<span data-ttu-id="e6ce6-262">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-262">String</span></span>|  
|<span data-ttu-id="e6ce6-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-263">DESCRIPTION</span></span>|<span data-ttu-id="e6ce6-264">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="e6ce6-265">Índices</span><span class="sxs-lookup"><span data-stu-id="e6ce6-265">Indexes</span></span>  
  
|<span data-ttu-id="e6ce6-266">ColumName</span><span class="sxs-lookup"><span data-stu-id="e6ce6-266">ColumnName</span></span>|<span data-ttu-id="e6ce6-267">DataType</span><span class="sxs-lookup"><span data-stu-id="e6ce6-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e6ce6-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-268">TABLE_CATALOG</span></span>|<span data-ttu-id="e6ce6-269">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-269">String</span></span>|  
|<span data-ttu-id="e6ce6-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="e6ce6-271">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-271">String</span></span>|  
|<span data-ttu-id="e6ce6-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-272">TABLE_NAME</span></span>|<span data-ttu-id="e6ce6-273">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-273">String</span></span>|  
|<span data-ttu-id="e6ce6-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-274">INDEX_CATALOG</span></span>|<span data-ttu-id="e6ce6-275">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-275">String</span></span>|  
|<span data-ttu-id="e6ce6-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="e6ce6-277">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-277">String</span></span>|  
|<span data-ttu-id="e6ce6-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-278">INDEX_NAME</span></span>|<span data-ttu-id="e6ce6-279">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-279">String</span></span>|  
|<span data-ttu-id="e6ce6-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="e6ce6-280">PRIMARY_KEY</span></span>|<span data-ttu-id="e6ce6-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-281">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-282">UNIQUE</span></span>|<span data-ttu-id="e6ce6-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-283">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-284">CLUSTERED</span></span>|<span data-ttu-id="e6ce6-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-285">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-286">TYPE</span></span>|<span data-ttu-id="e6ce6-287">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-287">Int32</span></span>|  
|<span data-ttu-id="e6ce6-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="e6ce6-288">FILL_FACTOR</span></span>|<span data-ttu-id="e6ce6-289">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-289">Int32</span></span>|  
|<span data-ttu-id="e6ce6-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-290">INITIAL_SIZE</span></span>|<span data-ttu-id="e6ce6-291">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-291">Int32</span></span>|  
|<span data-ttu-id="e6ce6-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="e6ce6-292">NULLS</span></span>|<span data-ttu-id="e6ce6-293">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-293">Int32</span></span>|  
|<span data-ttu-id="e6ce6-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="e6ce6-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="e6ce6-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-295">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-296">AUTO_UPDATE</span></span>|<span data-ttu-id="e6ce6-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-297">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-298">NULL_COLLATION</span></span>|<span data-ttu-id="e6ce6-299">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-299">Int32</span></span>|  
|<span data-ttu-id="e6ce6-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="e6ce6-301">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-301">Int64</span></span>|  
|<span data-ttu-id="e6ce6-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-302">COLUMN_NAME</span></span>|<span data-ttu-id="e6ce6-303">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-303">String</span></span>|  
|<span data-ttu-id="e6ce6-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-304">COLUMN_GUID</span></span>|<span data-ttu-id="e6ce6-305">Guid</span><span class="sxs-lookup"><span data-stu-id="e6ce6-305">Guid</span></span>|  
|<span data-ttu-id="e6ce6-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-306">COLUMN_PROPID</span></span>|<span data-ttu-id="e6ce6-307">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-307">Int64</span></span>|  
|<span data-ttu-id="e6ce6-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-308">COLLATION</span></span>|<span data-ttu-id="e6ce6-309">Int16</span><span class="sxs-lookup"><span data-stu-id="e6ce6-309">Int16</span></span>|  
|<span data-ttu-id="e6ce6-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="e6ce6-310">CARDINALITY</span></span>|<span data-ttu-id="e6ce6-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="e6ce6-311">Decimal</span></span>|  
|<span data-ttu-id="e6ce6-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="e6ce6-312">PAGES</span></span>|<span data-ttu-id="e6ce6-313">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-313">Int32</span></span>|  
|<span data-ttu-id="e6ce6-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-314">FILTER_CONDITION</span></span>|<span data-ttu-id="e6ce6-315">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-315">String</span></span>|  
|<span data-ttu-id="e6ce6-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-316">INTEGRATED</span></span>|<span data-ttu-id="e6ce6-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="e6ce6-318">Proveedor OLE DB de Microsoft para Oracle</span><span class="sxs-lookup"><span data-stu-id="e6ce6-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="e6ce6-319">El controlador OLE DB de Microsoft para Oracle admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="e6ce6-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="e6ce6-320">Tablas</span><span class="sxs-lookup"><span data-stu-id="e6ce6-320">Tables</span></span>  
  
-   <span data-ttu-id="e6ce6-321">Columnas</span><span class="sxs-lookup"><span data-stu-id="e6ce6-321">Columns</span></span>  
  
-   <span data-ttu-id="e6ce6-322">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="e6ce6-322">Procedures</span></span>  
  
-   <span data-ttu-id="e6ce6-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e6ce6-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="e6ce6-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="e6ce6-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="e6ce6-325">Vistas</span><span class="sxs-lookup"><span data-stu-id="e6ce6-325">Views</span></span>  
  
-   <span data-ttu-id="e6ce6-326">Índices</span><span class="sxs-lookup"><span data-stu-id="e6ce6-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="e6ce6-327">Tablas</span><span class="sxs-lookup"><span data-stu-id="e6ce6-327">Tables</span></span>  
  
|<span data-ttu-id="e6ce6-328">ColumName</span><span class="sxs-lookup"><span data-stu-id="e6ce6-328">ColumnName</span></span>|<span data-ttu-id="e6ce6-329">DataType</span><span class="sxs-lookup"><span data-stu-id="e6ce6-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e6ce6-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-330">TABLE_CATALOG</span></span>|<span data-ttu-id="e6ce6-331">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-331">String</span></span>|  
|<span data-ttu-id="e6ce6-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="e6ce6-333">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-333">String</span></span>|  
|<span data-ttu-id="e6ce6-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-334">TABLE_NAME</span></span>|<span data-ttu-id="e6ce6-335">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-335">String</span></span>|  
|<span data-ttu-id="e6ce6-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-336">TABLE_TYPE</span></span>|<span data-ttu-id="e6ce6-337">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-337">String</span></span>|  
|<span data-ttu-id="e6ce6-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-338">TABLE_GUID</span></span>|<span data-ttu-id="e6ce6-339">Guid</span><span class="sxs-lookup"><span data-stu-id="e6ce6-339">Guid</span></span>|  
|<span data-ttu-id="e6ce6-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-340">DESCRIPTION</span></span>|<span data-ttu-id="e6ce6-341">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-341">String</span></span>|  
|<span data-ttu-id="e6ce6-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-342">TABLE_PROPID</span></span>|<span data-ttu-id="e6ce6-343">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-343">Int64</span></span>|  
|<span data-ttu-id="e6ce6-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-344">DATE_CREATED</span></span>|<span data-ttu-id="e6ce6-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="e6ce6-345">DateTime</span></span>|  
|<span data-ttu-id="e6ce6-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-346">DATE_MODIFIED</span></span>|<span data-ttu-id="e6ce6-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="e6ce6-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e6ce6-348">Columnas</span><span class="sxs-lookup"><span data-stu-id="e6ce6-348">Columns</span></span>  
  
|<span data-ttu-id="e6ce6-349">ColumName</span><span class="sxs-lookup"><span data-stu-id="e6ce6-349">ColumnName</span></span>|<span data-ttu-id="e6ce6-350">DataType</span><span class="sxs-lookup"><span data-stu-id="e6ce6-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e6ce6-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-351">TABLE_CATALOG</span></span>|<span data-ttu-id="e6ce6-352">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-352">String</span></span>|  
|<span data-ttu-id="e6ce6-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="e6ce6-354">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-354">String</span></span>|  
|<span data-ttu-id="e6ce6-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-355">TABLE_NAME</span></span>|<span data-ttu-id="e6ce6-356">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-356">String</span></span>|  
|<span data-ttu-id="e6ce6-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-357">COLUMN_NAME</span></span>|<span data-ttu-id="e6ce6-358">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-358">String</span></span>|  
|<span data-ttu-id="e6ce6-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-359">COLUMN_GUID</span></span>|<span data-ttu-id="e6ce6-360">Guid</span><span class="sxs-lookup"><span data-stu-id="e6ce6-360">Guid</span></span>|  
|<span data-ttu-id="e6ce6-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-361">COLUMN_PROPID</span></span>|<span data-ttu-id="e6ce6-362">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-362">Int64</span></span>|  
|<span data-ttu-id="e6ce6-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="e6ce6-364">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-364">Int64</span></span>|  
|<span data-ttu-id="e6ce6-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="e6ce6-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="e6ce6-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-366">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e6ce6-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="e6ce6-368">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-368">String</span></span>|  
|<span data-ttu-id="e6ce6-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="e6ce6-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="e6ce6-370">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-370">Int64</span></span>|  
|<span data-ttu-id="e6ce6-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-371">IS_NULLABLE</span></span>|<span data-ttu-id="e6ce6-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-372">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-373">DATA_TYPE</span></span>|<span data-ttu-id="e6ce6-374">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-374">Int32</span></span>|  
|<span data-ttu-id="e6ce6-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-375">TYPE_GUID</span></span>|<span data-ttu-id="e6ce6-376">Guid</span><span class="sxs-lookup"><span data-stu-id="e6ce6-376">Guid</span></span>|  
|<span data-ttu-id="e6ce6-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e6ce6-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="e6ce6-378">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-378">Int64</span></span>|  
|<span data-ttu-id="e6ce6-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e6ce6-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="e6ce6-380">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-380">Int64</span></span>|  
|<span data-ttu-id="e6ce6-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="e6ce6-382">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-382">Int32</span></span>|  
|<span data-ttu-id="e6ce6-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="e6ce6-384">Int16</span><span class="sxs-lookup"><span data-stu-id="e6ce6-384">Int16</span></span>|  
|<span data-ttu-id="e6ce6-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="e6ce6-386">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-386">Int64</span></span>|  
|<span data-ttu-id="e6ce6-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="e6ce6-388">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-388">String</span></span>|  
|<span data-ttu-id="e6ce6-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="e6ce6-390">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-390">String</span></span>|  
|<span data-ttu-id="e6ce6-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="e6ce6-392">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-392">String</span></span>|  
|<span data-ttu-id="e6ce6-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="e6ce6-394">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-394">String</span></span>|  
|<span data-ttu-id="e6ce6-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="e6ce6-396">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-396">String</span></span>|  
|<span data-ttu-id="e6ce6-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-397">COLLATION_NAME</span></span>|<span data-ttu-id="e6ce6-398">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-398">String</span></span>|  
|<span data-ttu-id="e6ce6-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="e6ce6-400">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-400">String</span></span>|  
|<span data-ttu-id="e6ce6-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="e6ce6-402">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-402">String</span></span>|  
|<span data-ttu-id="e6ce6-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-403">DOMAIN_NAME</span></span>|<span data-ttu-id="e6ce6-404">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-404">String</span></span>|  
|<span data-ttu-id="e6ce6-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-405">DESCRIPTION</span></span>|<span data-ttu-id="e6ce6-406">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e6ce6-407">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="e6ce6-407">Procedures</span></span>  
  
|<span data-ttu-id="e6ce6-408">ColumName</span><span class="sxs-lookup"><span data-stu-id="e6ce6-408">ColumnName</span></span>|<span data-ttu-id="e6ce6-409">DataType</span><span class="sxs-lookup"><span data-stu-id="e6ce6-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e6ce6-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="e6ce6-411">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-411">String</span></span>|  
|<span data-ttu-id="e6ce6-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="e6ce6-413">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-413">String</span></span>|  
|<span data-ttu-id="e6ce6-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="e6ce6-415">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-415">String</span></span>|  
|<span data-ttu-id="e6ce6-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e6ce6-417">Int16</span><span class="sxs-lookup"><span data-stu-id="e6ce6-417">Int16</span></span>|  
|<span data-ttu-id="e6ce6-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="e6ce6-419">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-419">String</span></span>|  
|<span data-ttu-id="e6ce6-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-420">DESCRIPTION</span></span>|<span data-ttu-id="e6ce6-421">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-421">String</span></span>|  
|<span data-ttu-id="e6ce6-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-422">DATE_CREATED</span></span>|<span data-ttu-id="e6ce6-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="e6ce6-423">DateTime</span></span>|  
|<span data-ttu-id="e6ce6-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-424">DATE_MODIFIED</span></span>|<span data-ttu-id="e6ce6-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="e6ce6-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="e6ce6-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="e6ce6-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="e6ce6-427">ColumName</span><span class="sxs-lookup"><span data-stu-id="e6ce6-427">ColumnName</span></span>|<span data-ttu-id="e6ce6-428">DataType</span><span class="sxs-lookup"><span data-stu-id="e6ce6-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e6ce6-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="e6ce6-430">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-430">String</span></span>|  
|<span data-ttu-id="e6ce6-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="e6ce6-432">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-432">String</span></span>|  
|<span data-ttu-id="e6ce6-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="e6ce6-434">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-434">String</span></span>|  
|<span data-ttu-id="e6ce6-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-435">COLUMN_NAME</span></span>|<span data-ttu-id="e6ce6-436">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-436">String</span></span>|  
|<span data-ttu-id="e6ce6-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-437">COLUMN_GUID</span></span>|<span data-ttu-id="e6ce6-438">Guid</span><span class="sxs-lookup"><span data-stu-id="e6ce6-438">Guid</span></span>|  
|<span data-ttu-id="e6ce6-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-439">COLUMN_PROPID</span></span>|<span data-ttu-id="e6ce6-440">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-440">Int64</span></span>|  
|<span data-ttu-id="e6ce6-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="e6ce6-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="e6ce6-442">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-442">Int64</span></span>|  
|<span data-ttu-id="e6ce6-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="e6ce6-444">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-444">Int64</span></span>|  
|<span data-ttu-id="e6ce6-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-445">IS_NULLABLE</span></span>|<span data-ttu-id="e6ce6-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-446">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-447">DATA_TYPE</span></span>|<span data-ttu-id="e6ce6-448">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-448">Int32</span></span>|  
|<span data-ttu-id="e6ce6-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-449">TYPE_GUID</span></span>|<span data-ttu-id="e6ce6-450">Guid</span><span class="sxs-lookup"><span data-stu-id="e6ce6-450">Guid</span></span>|  
|<span data-ttu-id="e6ce6-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e6ce6-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="e6ce6-452">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-452">Int64</span></span>|  
|<span data-ttu-id="e6ce6-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e6ce6-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="e6ce6-454">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-454">Int64</span></span>|  
|<span data-ttu-id="e6ce6-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="e6ce6-456">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-456">Int32</span></span>|  
|<span data-ttu-id="e6ce6-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="e6ce6-458">Int16</span><span class="sxs-lookup"><span data-stu-id="e6ce6-458">Int16</span></span>|  
|<span data-ttu-id="e6ce6-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-459">DESCRIPTION</span></span>|<span data-ttu-id="e6ce6-460">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-460">String</span></span>|  
|<span data-ttu-id="e6ce6-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="e6ce6-461">OVERLOAD</span></span>|<span data-ttu-id="e6ce6-462">Int16</span><span class="sxs-lookup"><span data-stu-id="e6ce6-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="e6ce6-463">Vistas</span><span class="sxs-lookup"><span data-stu-id="e6ce6-463">Views</span></span>  
  
|<span data-ttu-id="e6ce6-464">ColumName</span><span class="sxs-lookup"><span data-stu-id="e6ce6-464">ColumnName</span></span>|<span data-ttu-id="e6ce6-465">DataType</span><span class="sxs-lookup"><span data-stu-id="e6ce6-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e6ce6-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-466">TABLE_CATALOG</span></span>|<span data-ttu-id="e6ce6-467">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-467">String</span></span>|  
|<span data-ttu-id="e6ce6-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="e6ce6-469">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-469">String</span></span>|  
|<span data-ttu-id="e6ce6-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-470">TABLE_NAME</span></span>|<span data-ttu-id="e6ce6-471">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-471">String</span></span>|  
|<span data-ttu-id="e6ce6-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="e6ce6-473">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-473">String</span></span>|  
|<span data-ttu-id="e6ce6-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-474">CHECK_OPTION</span></span>|<span data-ttu-id="e6ce6-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-475">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-476">IS_UPDATABLE</span></span>|<span data-ttu-id="e6ce6-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-477">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-478">DESCRIPTION</span></span>|<span data-ttu-id="e6ce6-479">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-479">String</span></span>|  
|<span data-ttu-id="e6ce6-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-480">DATE_CREATED</span></span>|<span data-ttu-id="e6ce6-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="e6ce6-481">DateTime</span></span>|  
|<span data-ttu-id="e6ce6-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-482">DATE_MODIFIED</span></span>|<span data-ttu-id="e6ce6-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="e6ce6-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="e6ce6-484">Índices</span><span class="sxs-lookup"><span data-stu-id="e6ce6-484">Indexes</span></span>  
  
|<span data-ttu-id="e6ce6-485">ColumName</span><span class="sxs-lookup"><span data-stu-id="e6ce6-485">ColumnName</span></span>|<span data-ttu-id="e6ce6-486">DataType</span><span class="sxs-lookup"><span data-stu-id="e6ce6-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e6ce6-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-487">TABLE_CATALOG</span></span>|<span data-ttu-id="e6ce6-488">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-488">String</span></span>|  
|<span data-ttu-id="e6ce6-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="e6ce6-490">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-490">String</span></span>|  
|<span data-ttu-id="e6ce6-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-491">TABLE_NAME</span></span>|<span data-ttu-id="e6ce6-492">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-492">String</span></span>|  
|<span data-ttu-id="e6ce6-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-493">INDEX_CATALOG</span></span>|<span data-ttu-id="e6ce6-494">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-494">String</span></span>|  
|<span data-ttu-id="e6ce6-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="e6ce6-496">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-496">String</span></span>|  
|<span data-ttu-id="e6ce6-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-497">INDEX_NAME</span></span>|<span data-ttu-id="e6ce6-498">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-498">String</span></span>|  
|<span data-ttu-id="e6ce6-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="e6ce6-499">PRIMARY_KEY</span></span>|<span data-ttu-id="e6ce6-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-500">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-501">UNIQUE</span></span>|<span data-ttu-id="e6ce6-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-502">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-503">CLUSTERED</span></span>|<span data-ttu-id="e6ce6-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-504">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-505">TYPE</span></span>|<span data-ttu-id="e6ce6-506">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-506">Int32</span></span>|  
|<span data-ttu-id="e6ce6-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="e6ce6-507">FILL_FACTOR</span></span>|<span data-ttu-id="e6ce6-508">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-508">Int32</span></span>|  
|<span data-ttu-id="e6ce6-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-509">INITIAL_SIZE</span></span>|<span data-ttu-id="e6ce6-510">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-510">Int32</span></span>|  
|<span data-ttu-id="e6ce6-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="e6ce6-511">NULLS</span></span>|<span data-ttu-id="e6ce6-512">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-512">Int32</span></span>|  
|<span data-ttu-id="e6ce6-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="e6ce6-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="e6ce6-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-514">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-515">AUTO_UPDATE</span></span>|<span data-ttu-id="e6ce6-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-516">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-517">NULL_COLLATION</span></span>|<span data-ttu-id="e6ce6-518">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-518">Int32</span></span>|  
|<span data-ttu-id="e6ce6-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="e6ce6-520">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-520">Int64</span></span>|  
|<span data-ttu-id="e6ce6-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-521">COLUMN_NAME</span></span>|<span data-ttu-id="e6ce6-522">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-522">String</span></span>|  
|<span data-ttu-id="e6ce6-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-523">COLUMN_GUID</span></span>|<span data-ttu-id="e6ce6-524">Guid</span><span class="sxs-lookup"><span data-stu-id="e6ce6-524">Guid</span></span>|  
|<span data-ttu-id="e6ce6-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-525">COLUMN_PROPID</span></span>|<span data-ttu-id="e6ce6-526">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-526">Int64</span></span>|  
|<span data-ttu-id="e6ce6-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-527">COLLATION</span></span>|<span data-ttu-id="e6ce6-528">Int16</span><span class="sxs-lookup"><span data-stu-id="e6ce6-528">Int16</span></span>|  
|<span data-ttu-id="e6ce6-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="e6ce6-529">CARDINALITY</span></span>|<span data-ttu-id="e6ce6-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="e6ce6-530">Decimal</span></span>|  
|<span data-ttu-id="e6ce6-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="e6ce6-531">PAGES</span></span>|<span data-ttu-id="e6ce6-532">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-532">Int32</span></span>|  
|<span data-ttu-id="e6ce6-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-533">FILTER_CONDITION</span></span>|<span data-ttu-id="e6ce6-534">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-534">String</span></span>|  
|<span data-ttu-id="e6ce6-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-535">INTEGRATED</span></span>|<span data-ttu-id="e6ce6-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="e6ce6-537">Proveedor OLE DB de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="e6ce6-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="e6ce6-538">El controlador OLE DB de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="e6ce6-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="e6ce6-539">Tablas</span><span class="sxs-lookup"><span data-stu-id="e6ce6-539">Tables</span></span>  
  
-   <span data-ttu-id="e6ce6-540">Columnas</span><span class="sxs-lookup"><span data-stu-id="e6ce6-540">Columns</span></span>  
  
-   <span data-ttu-id="e6ce6-541">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="e6ce6-541">Procedures</span></span>  
  
-   <span data-ttu-id="e6ce6-542">Vistas</span><span class="sxs-lookup"><span data-stu-id="e6ce6-542">Views</span></span>  
  
-   <span data-ttu-id="e6ce6-543">Índices</span><span class="sxs-lookup"><span data-stu-id="e6ce6-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="e6ce6-544">Tablas</span><span class="sxs-lookup"><span data-stu-id="e6ce6-544">Tables</span></span>  
  
|<span data-ttu-id="e6ce6-545">ColumName</span><span class="sxs-lookup"><span data-stu-id="e6ce6-545">ColumnName</span></span>|<span data-ttu-id="e6ce6-546">DataType</span><span class="sxs-lookup"><span data-stu-id="e6ce6-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e6ce6-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-547">TABLE_CATALOG</span></span>|<span data-ttu-id="e6ce6-548">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-548">String</span></span>|  
|<span data-ttu-id="e6ce6-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="e6ce6-550">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-550">String</span></span>|  
|<span data-ttu-id="e6ce6-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-551">TABLE_NAME</span></span>|<span data-ttu-id="e6ce6-552">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-552">String</span></span>|  
|<span data-ttu-id="e6ce6-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-553">TABLE_TYPE</span></span>|<span data-ttu-id="e6ce6-554">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-554">String</span></span>|  
|<span data-ttu-id="e6ce6-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-555">TABLE_GUID</span></span>|<span data-ttu-id="e6ce6-556">Guid</span><span class="sxs-lookup"><span data-stu-id="e6ce6-556">Guid</span></span>|  
|<span data-ttu-id="e6ce6-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-557">DESCRIPTION</span></span>|<span data-ttu-id="e6ce6-558">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-558">String</span></span>|  
|<span data-ttu-id="e6ce6-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-559">TABLE_PROPID</span></span>|<span data-ttu-id="e6ce6-560">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-560">Int64</span></span>|  
|<span data-ttu-id="e6ce6-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-561">DATE_CREATED</span></span>|<span data-ttu-id="e6ce6-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="e6ce6-562">DateTime</span></span>|  
|<span data-ttu-id="e6ce6-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-563">DATE_MODIFIED</span></span>|<span data-ttu-id="e6ce6-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="e6ce6-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="e6ce6-565">Columnas</span><span class="sxs-lookup"><span data-stu-id="e6ce6-565">Columns</span></span>  
  
|<span data-ttu-id="e6ce6-566">ColumName</span><span class="sxs-lookup"><span data-stu-id="e6ce6-566">ColumnName</span></span>|<span data-ttu-id="e6ce6-567">DataType</span><span class="sxs-lookup"><span data-stu-id="e6ce6-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e6ce6-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-568">TABLE_CATALOG</span></span>|<span data-ttu-id="e6ce6-569">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-569">String</span></span>|  
|<span data-ttu-id="e6ce6-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="e6ce6-571">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-571">String</span></span>|  
|<span data-ttu-id="e6ce6-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-572">TABLE_NAME</span></span>|<span data-ttu-id="e6ce6-573">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-573">String</span></span>|  
|<span data-ttu-id="e6ce6-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-574">COLUMN_NAME</span></span>|<span data-ttu-id="e6ce6-575">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-575">String</span></span>|  
|<span data-ttu-id="e6ce6-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-576">COLUMN_GUID</span></span>|<span data-ttu-id="e6ce6-577">Guid</span><span class="sxs-lookup"><span data-stu-id="e6ce6-577">Guid</span></span>|  
|<span data-ttu-id="e6ce6-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-578">COLUMN_PROPID</span></span>|<span data-ttu-id="e6ce6-579">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-579">Int64</span></span>|  
|<span data-ttu-id="e6ce6-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="e6ce6-581">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-581">Int64</span></span>|  
|<span data-ttu-id="e6ce6-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="e6ce6-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="e6ce6-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-583">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e6ce6-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="e6ce6-585">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-585">String</span></span>|  
|<span data-ttu-id="e6ce6-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="e6ce6-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="e6ce6-587">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-587">Int64</span></span>|  
|<span data-ttu-id="e6ce6-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-588">IS_NULLABLE</span></span>|<span data-ttu-id="e6ce6-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-589">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-590">DATA_TYPE</span></span>|<span data-ttu-id="e6ce6-591">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-591">Int32</span></span>|  
|<span data-ttu-id="e6ce6-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-592">TYPE_GUID</span></span>|<span data-ttu-id="e6ce6-593">Guid</span><span class="sxs-lookup"><span data-stu-id="e6ce6-593">Guid</span></span>|  
|<span data-ttu-id="e6ce6-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e6ce6-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="e6ce6-595">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-595">Int64</span></span>|  
|<span data-ttu-id="e6ce6-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e6ce6-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="e6ce6-597">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-597">Int64</span></span>|  
|<span data-ttu-id="e6ce6-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="e6ce6-599">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-599">Int32</span></span>|  
|<span data-ttu-id="e6ce6-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="e6ce6-601">Int16</span><span class="sxs-lookup"><span data-stu-id="e6ce6-601">Int16</span></span>|  
|<span data-ttu-id="e6ce6-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="e6ce6-603">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-603">Int64</span></span>|  
|<span data-ttu-id="e6ce6-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="e6ce6-605">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-605">String</span></span>|  
|<span data-ttu-id="e6ce6-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="e6ce6-607">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-607">String</span></span>|  
|<span data-ttu-id="e6ce6-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="e6ce6-609">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-609">String</span></span>|  
|<span data-ttu-id="e6ce6-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="e6ce6-611">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-611">String</span></span>|  
|<span data-ttu-id="e6ce6-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="e6ce6-613">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-613">String</span></span>|  
|<span data-ttu-id="e6ce6-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-614">COLLATION_NAME</span></span>|<span data-ttu-id="e6ce6-615">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-615">String</span></span>|  
|<span data-ttu-id="e6ce6-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="e6ce6-617">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-617">String</span></span>|  
|<span data-ttu-id="e6ce6-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="e6ce6-619">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-619">String</span></span>|  
|<span data-ttu-id="e6ce6-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-620">DOMAIN_NAME</span></span>|<span data-ttu-id="e6ce6-621">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-621">String</span></span>|  
|<span data-ttu-id="e6ce6-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-622">DESCRIPTION</span></span>|<span data-ttu-id="e6ce6-623">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="e6ce6-624">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="e6ce6-624">Procedures</span></span>  
  
|<span data-ttu-id="e6ce6-625">ColumName</span><span class="sxs-lookup"><span data-stu-id="e6ce6-625">ColumnName</span></span>|<span data-ttu-id="e6ce6-626">DataType</span><span class="sxs-lookup"><span data-stu-id="e6ce6-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e6ce6-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="e6ce6-628">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-628">String</span></span>|  
|<span data-ttu-id="e6ce6-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="e6ce6-630">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-630">String</span></span>|  
|<span data-ttu-id="e6ce6-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="e6ce6-632">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-632">String</span></span>|  
|<span data-ttu-id="e6ce6-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="e6ce6-634">Int16</span><span class="sxs-lookup"><span data-stu-id="e6ce6-634">Int16</span></span>|  
|<span data-ttu-id="e6ce6-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="e6ce6-636">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-636">String</span></span>|  
|<span data-ttu-id="e6ce6-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-637">DESCRIPTION</span></span>|<span data-ttu-id="e6ce6-638">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-638">String</span></span>|  
|<span data-ttu-id="e6ce6-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-639">DATE_CREATED</span></span>|<span data-ttu-id="e6ce6-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="e6ce6-640">DateTime</span></span>|  
|<span data-ttu-id="e6ce6-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-641">DATE_MODIFIED</span></span>|<span data-ttu-id="e6ce6-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="e6ce6-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="e6ce6-643">Vistas</span><span class="sxs-lookup"><span data-stu-id="e6ce6-643">Views</span></span>  
  
|<span data-ttu-id="e6ce6-644">ColumName</span><span class="sxs-lookup"><span data-stu-id="e6ce6-644">ColumnName</span></span>|<span data-ttu-id="e6ce6-645">DataType</span><span class="sxs-lookup"><span data-stu-id="e6ce6-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e6ce6-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-646">TABLE_CATALOG</span></span>|<span data-ttu-id="e6ce6-647">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-647">String</span></span>|  
|<span data-ttu-id="e6ce6-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="e6ce6-649">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-649">String</span></span>|  
|<span data-ttu-id="e6ce6-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-650">TABLE_NAME</span></span>|<span data-ttu-id="e6ce6-651">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-651">String</span></span>|  
|<span data-ttu-id="e6ce6-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="e6ce6-653">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-653">String</span></span>|  
|<span data-ttu-id="e6ce6-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-654">CHECK_OPTION</span></span>|<span data-ttu-id="e6ce6-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-655">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-656">IS_UPDATABLE</span></span>|<span data-ttu-id="e6ce6-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-657">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-658">DESCRIPTION</span></span>|<span data-ttu-id="e6ce6-659">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-659">String</span></span>|  
|<span data-ttu-id="e6ce6-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-660">DATE_CREATED</span></span>|<span data-ttu-id="e6ce6-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="e6ce6-661">DateTime</span></span>|  
|<span data-ttu-id="e6ce6-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-662">DATE_MODIFIED</span></span>|<span data-ttu-id="e6ce6-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="e6ce6-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="e6ce6-664">Índices</span><span class="sxs-lookup"><span data-stu-id="e6ce6-664">Indexes</span></span>  
  
|<span data-ttu-id="e6ce6-665">ColumName</span><span class="sxs-lookup"><span data-stu-id="e6ce6-665">ColumnName</span></span>|<span data-ttu-id="e6ce6-666">DataType</span><span class="sxs-lookup"><span data-stu-id="e6ce6-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="e6ce6-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-667">TABLE_CATALOG</span></span>|<span data-ttu-id="e6ce6-668">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-668">String</span></span>|  
|<span data-ttu-id="e6ce6-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="e6ce6-670">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-670">String</span></span>|  
|<span data-ttu-id="e6ce6-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-671">TABLE_NAME</span></span>|<span data-ttu-id="e6ce6-672">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-672">String</span></span>|  
|<span data-ttu-id="e6ce6-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="e6ce6-673">INDEX_CATALOG</span></span>|<span data-ttu-id="e6ce6-674">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-674">String</span></span>|  
|<span data-ttu-id="e6ce6-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="e6ce6-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="e6ce6-676">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-676">String</span></span>|  
|<span data-ttu-id="e6ce6-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-677">INDEX_NAME</span></span>|<span data-ttu-id="e6ce6-678">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-678">String</span></span>|  
|<span data-ttu-id="e6ce6-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="e6ce6-679">PRIMARY_KEY</span></span>|<span data-ttu-id="e6ce6-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-680">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-681">UNIQUE</span></span>|<span data-ttu-id="e6ce6-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-682">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-683">CLUSTERED</span></span>|<span data-ttu-id="e6ce6-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-684">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-685">TYPE</span></span>|<span data-ttu-id="e6ce6-686">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-686">Int32</span></span>|  
|<span data-ttu-id="e6ce6-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="e6ce6-687">FILL_FACTOR</span></span>|<span data-ttu-id="e6ce6-688">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-688">Int32</span></span>|  
|<span data-ttu-id="e6ce6-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-689">INITIAL_SIZE</span></span>|<span data-ttu-id="e6ce6-690">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-690">Int32</span></span>|  
|<span data-ttu-id="e6ce6-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="e6ce6-691">NULLS</span></span>|<span data-ttu-id="e6ce6-692">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-692">Int32</span></span>|  
|<span data-ttu-id="e6ce6-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="e6ce6-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="e6ce6-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-694">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="e6ce6-695">AUTO_UPDATE</span></span>|<span data-ttu-id="e6ce6-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="e6ce6-696">Boolean</span></span>|  
|<span data-ttu-id="e6ce6-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-697">NULL_COLLATION</span></span>|<span data-ttu-id="e6ce6-698">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-698">Int32</span></span>|  
|<span data-ttu-id="e6ce6-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="e6ce6-700">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-700">Int64</span></span>|  
|<span data-ttu-id="e6ce6-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="e6ce6-701">COLUMN_NAME</span></span>|<span data-ttu-id="e6ce6-702">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-702">String</span></span>|  
|<span data-ttu-id="e6ce6-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-703">COLUMN_GUID</span></span>|<span data-ttu-id="e6ce6-704">Guid</span><span class="sxs-lookup"><span data-stu-id="e6ce6-704">Guid</span></span>|  
|<span data-ttu-id="e6ce6-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="e6ce6-705">COLUMN_PROPID</span></span>|<span data-ttu-id="e6ce6-706">Int64</span><span class="sxs-lookup"><span data-stu-id="e6ce6-706">Int64</span></span>|  
|<span data-ttu-id="e6ce6-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-707">COLLATION</span></span>|<span data-ttu-id="e6ce6-708">Int16</span><span class="sxs-lookup"><span data-stu-id="e6ce6-708">Int16</span></span>|  
|<span data-ttu-id="e6ce6-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="e6ce6-709">CARDINALITY</span></span>|<span data-ttu-id="e6ce6-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="e6ce6-710">Decimal</span></span>|  
|<span data-ttu-id="e6ce6-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="e6ce6-711">PAGES</span></span>|<span data-ttu-id="e6ce6-712">Int32</span><span class="sxs-lookup"><span data-stu-id="e6ce6-712">Int32</span></span>|  
|<span data-ttu-id="e6ce6-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="e6ce6-713">FILTER_CONDITION</span></span>|<span data-ttu-id="e6ce6-714">String</span><span class="sxs-lookup"><span data-stu-id="e6ce6-714">String</span></span>|  
|<span data-ttu-id="e6ce6-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="e6ce6-715">INTEGRATED</span></span>|<span data-ttu-id="e6ce6-716">Booleano</span><span class="sxs-lookup"><span data-stu-id="e6ce6-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e6ce6-717">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6ce6-717">See Also</span></span>  
 [<span data-ttu-id="e6ce6-718">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="e6ce6-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
