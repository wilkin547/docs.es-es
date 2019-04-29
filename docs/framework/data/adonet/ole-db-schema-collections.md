---
title: Colecciones de esquemas de OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6dc187b0a876d9e167a74f2381db156dde2764fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772000"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="6649e-102">Colecciones de esquemas de OLE DB</span><span class="sxs-lookup"><span data-stu-id="6649e-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="6649e-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los proveedores OLE DB de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="6649e-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="6649e-104">Proveedor OLE DB para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="6649e-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="6649e-105">El controlador OLE DB de Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:</span><span class="sxs-lookup"><span data-stu-id="6649e-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="6649e-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="6649e-106">Tables</span></span>  
  
- <span data-ttu-id="6649e-107">Columnas</span><span class="sxs-lookup"><span data-stu-id="6649e-107">Columns</span></span>  
  
- <span data-ttu-id="6649e-108">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="6649e-108">Procedures</span></span>  
  
- <span data-ttu-id="6649e-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="6649e-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="6649e-110">Catálogo</span><span class="sxs-lookup"><span data-stu-id="6649e-110">Catalog</span></span>  
  
- <span data-ttu-id="6649e-111">Índices</span><span class="sxs-lookup"><span data-stu-id="6649e-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="6649e-112">Tablas</span><span class="sxs-lookup"><span data-stu-id="6649e-112">Tables</span></span>  
  
|<span data-ttu-id="6649e-113">ColumName</span><span class="sxs-lookup"><span data-stu-id="6649e-113">ColumnName</span></span>|<span data-ttu-id="6649e-114">DataType</span><span class="sxs-lookup"><span data-stu-id="6649e-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6649e-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-115">TABLE_CATALOG</span></span>|<span data-ttu-id="6649e-116">String</span><span class="sxs-lookup"><span data-stu-id="6649e-116">String</span></span>|  
|<span data-ttu-id="6649e-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="6649e-118">String</span><span class="sxs-lookup"><span data-stu-id="6649e-118">String</span></span>|  
|<span data-ttu-id="6649e-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-119">TABLE_NAME</span></span>|<span data-ttu-id="6649e-120">String</span><span class="sxs-lookup"><span data-stu-id="6649e-120">String</span></span>|  
|<span data-ttu-id="6649e-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="6649e-121">TABLE_TYPE</span></span>|<span data-ttu-id="6649e-122">String</span><span class="sxs-lookup"><span data-stu-id="6649e-122">String</span></span>|  
|<span data-ttu-id="6649e-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-123">TABLE_GUID</span></span>|<span data-ttu-id="6649e-124">GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-124">Guid</span></span>|  
|<span data-ttu-id="6649e-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6649e-125">DESCRIPTION</span></span>|<span data-ttu-id="6649e-126">String</span><span class="sxs-lookup"><span data-stu-id="6649e-126">String</span></span>|  
|<span data-ttu-id="6649e-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="6649e-127">TABLE_PROPID</span></span>|<span data-ttu-id="6649e-128">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-128">Int64</span></span>|  
|<span data-ttu-id="6649e-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="6649e-129">DATE_CREATED</span></span>|<span data-ttu-id="6649e-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="6649e-130">DateTime</span></span>|  
|<span data-ttu-id="6649e-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="6649e-131">DATE_MODIFIED</span></span>|<span data-ttu-id="6649e-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="6649e-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="6649e-133">Columnas</span><span class="sxs-lookup"><span data-stu-id="6649e-133">Columns</span></span>  
  
|<span data-ttu-id="6649e-134">ColumName</span><span class="sxs-lookup"><span data-stu-id="6649e-134">ColumnName</span></span>|<span data-ttu-id="6649e-135">DataType</span><span class="sxs-lookup"><span data-stu-id="6649e-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6649e-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-136">TABLE_CATALOG</span></span>|<span data-ttu-id="6649e-137">String</span><span class="sxs-lookup"><span data-stu-id="6649e-137">String</span></span>|  
|<span data-ttu-id="6649e-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="6649e-139">String</span><span class="sxs-lookup"><span data-stu-id="6649e-139">String</span></span>|  
|<span data-ttu-id="6649e-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-140">TABLE_NAME</span></span>|<span data-ttu-id="6649e-141">String</span><span class="sxs-lookup"><span data-stu-id="6649e-141">String</span></span>|  
|<span data-ttu-id="6649e-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-142">COLUMN_NAME</span></span>|<span data-ttu-id="6649e-143">String</span><span class="sxs-lookup"><span data-stu-id="6649e-143">String</span></span>|  
|<span data-ttu-id="6649e-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-144">COLUMN_GUID</span></span>|<span data-ttu-id="6649e-145">GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-145">Guid</span></span>|  
|<span data-ttu-id="6649e-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="6649e-146">COLUMN_PROPID</span></span>|<span data-ttu-id="6649e-147">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-147">Int64</span></span>|  
|<span data-ttu-id="6649e-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6649e-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="6649e-149">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-149">Int64</span></span>|  
|<span data-ttu-id="6649e-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="6649e-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="6649e-151">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-151">Boolean</span></span>|  
|<span data-ttu-id="6649e-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="6649e-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="6649e-153">String</span><span class="sxs-lookup"><span data-stu-id="6649e-153">String</span></span>|  
|<span data-ttu-id="6649e-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="6649e-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="6649e-155">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-155">Int64</span></span>|  
|<span data-ttu-id="6649e-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6649e-156">IS_NULLABLE</span></span>|<span data-ttu-id="6649e-157">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-157">Boolean</span></span>|  
|<span data-ttu-id="6649e-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6649e-158">DATA_TYPE</span></span>|<span data-ttu-id="6649e-159">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-159">Int32</span></span>|  
|<span data-ttu-id="6649e-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-160">TYPE_GUID</span></span>|<span data-ttu-id="6649e-161">GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-161">Guid</span></span>|  
|<span data-ttu-id="6649e-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6649e-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="6649e-163">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-163">Int64</span></span>|  
|<span data-ttu-id="6649e-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6649e-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="6649e-165">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-165">Int64</span></span>|  
|<span data-ttu-id="6649e-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="6649e-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="6649e-167">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-167">Int32</span></span>|  
|<span data-ttu-id="6649e-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="6649e-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="6649e-169">Int16</span><span class="sxs-lookup"><span data-stu-id="6649e-169">Int16</span></span>|  
|<span data-ttu-id="6649e-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="6649e-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="6649e-171">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-171">Int64</span></span>|  
|<span data-ttu-id="6649e-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="6649e-173">String</span><span class="sxs-lookup"><span data-stu-id="6649e-173">String</span></span>|  
|<span data-ttu-id="6649e-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="6649e-175">String</span><span class="sxs-lookup"><span data-stu-id="6649e-175">String</span></span>|  
|<span data-ttu-id="6649e-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="6649e-177">String</span><span class="sxs-lookup"><span data-stu-id="6649e-177">String</span></span>|  
|<span data-ttu-id="6649e-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="6649e-179">String</span><span class="sxs-lookup"><span data-stu-id="6649e-179">String</span></span>|  
|<span data-ttu-id="6649e-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="6649e-181">String</span><span class="sxs-lookup"><span data-stu-id="6649e-181">String</span></span>|  
|<span data-ttu-id="6649e-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-182">COLLATION_NAME</span></span>|<span data-ttu-id="6649e-183">String</span><span class="sxs-lookup"><span data-stu-id="6649e-183">String</span></span>|  
|<span data-ttu-id="6649e-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="6649e-185">String</span><span class="sxs-lookup"><span data-stu-id="6649e-185">String</span></span>|  
|<span data-ttu-id="6649e-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="6649e-187">String</span><span class="sxs-lookup"><span data-stu-id="6649e-187">String</span></span>|  
|<span data-ttu-id="6649e-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-188">DOMAIN_NAME</span></span>|<span data-ttu-id="6649e-189">String</span><span class="sxs-lookup"><span data-stu-id="6649e-189">String</span></span>|  
|<span data-ttu-id="6649e-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6649e-190">DESCRIPTION</span></span>|<span data-ttu-id="6649e-191">String</span><span class="sxs-lookup"><span data-stu-id="6649e-191">String</span></span>|  
|<span data-ttu-id="6649e-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="6649e-192">COLUMN_LCID</span></span>|<span data-ttu-id="6649e-193">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-193">Int32</span></span>|  
|<span data-ttu-id="6649e-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="6649e-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="6649e-195">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-195">Int32</span></span>|  
|<span data-ttu-id="6649e-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="6649e-196">COLUMN_SORTID</span></span>|<span data-ttu-id="6649e-197">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-197">Int32</span></span>|  
|<span data-ttu-id="6649e-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="6649e-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="6649e-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="6649e-199">Byte[]</span></span>|  
|<span data-ttu-id="6649e-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="6649e-200">IS_COMPUTED</span></span>|<span data-ttu-id="6649e-201">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="6649e-202">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="6649e-202">Procedures</span></span>  
  
|<span data-ttu-id="6649e-203">ColumName</span><span class="sxs-lookup"><span data-stu-id="6649e-203">ColumnName</span></span>|<span data-ttu-id="6649e-204">DataType</span><span class="sxs-lookup"><span data-stu-id="6649e-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6649e-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="6649e-206">String</span><span class="sxs-lookup"><span data-stu-id="6649e-206">String</span></span>|  
|<span data-ttu-id="6649e-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="6649e-208">String</span><span class="sxs-lookup"><span data-stu-id="6649e-208">String</span></span>|  
|<span data-ttu-id="6649e-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="6649e-210">String</span><span class="sxs-lookup"><span data-stu-id="6649e-210">String</span></span>|  
|<span data-ttu-id="6649e-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="6649e-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="6649e-212">Int16</span><span class="sxs-lookup"><span data-stu-id="6649e-212">Int16</span></span>|  
|<span data-ttu-id="6649e-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="6649e-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="6649e-214">String</span><span class="sxs-lookup"><span data-stu-id="6649e-214">String</span></span>|  
|<span data-ttu-id="6649e-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6649e-215">DESCRIPTION</span></span>|<span data-ttu-id="6649e-216">String</span><span class="sxs-lookup"><span data-stu-id="6649e-216">String</span></span>|  
|<span data-ttu-id="6649e-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="6649e-217">DATE_CREATED</span></span>|<span data-ttu-id="6649e-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="6649e-218">DateTime</span></span>|  
|<span data-ttu-id="6649e-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="6649e-219">DATE_MODIFIED</span></span>|<span data-ttu-id="6649e-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="6649e-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="6649e-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="6649e-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="6649e-222">ColumName</span><span class="sxs-lookup"><span data-stu-id="6649e-222">ColumnName</span></span>|<span data-ttu-id="6649e-223">DataType</span><span class="sxs-lookup"><span data-stu-id="6649e-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6649e-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="6649e-225">String</span><span class="sxs-lookup"><span data-stu-id="6649e-225">String</span></span>|  
|<span data-ttu-id="6649e-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="6649e-227">String</span><span class="sxs-lookup"><span data-stu-id="6649e-227">String</span></span>|  
|<span data-ttu-id="6649e-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="6649e-229">String</span><span class="sxs-lookup"><span data-stu-id="6649e-229">String</span></span>|  
|<span data-ttu-id="6649e-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-230">PARAMETER_NAME</span></span>|<span data-ttu-id="6649e-231">String</span><span class="sxs-lookup"><span data-stu-id="6649e-231">String</span></span>|  
|<span data-ttu-id="6649e-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6649e-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="6649e-233">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-233">Int32</span></span>|  
|<span data-ttu-id="6649e-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="6649e-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="6649e-235">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-235">Int32</span></span>|  
|<span data-ttu-id="6649e-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="6649e-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="6649e-237">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-237">Boolean</span></span>|  
|<span data-ttu-id="6649e-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="6649e-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="6649e-239">String</span><span class="sxs-lookup"><span data-stu-id="6649e-239">String</span></span>|  
|<span data-ttu-id="6649e-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6649e-240">IS_NULLABLE</span></span>|<span data-ttu-id="6649e-241">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-241">Boolean</span></span>|  
|<span data-ttu-id="6649e-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6649e-242">DATA_TYPE</span></span>|<span data-ttu-id="6649e-243">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-243">Int32</span></span>|  
|<span data-ttu-id="6649e-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6649e-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="6649e-245">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-245">Int64</span></span>|  
|<span data-ttu-id="6649e-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6649e-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="6649e-247">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-247">Int64</span></span>|  
|<span data-ttu-id="6649e-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="6649e-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="6649e-249">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-249">Int32</span></span>|  
|<span data-ttu-id="6649e-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="6649e-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="6649e-251">Int16</span><span class="sxs-lookup"><span data-stu-id="6649e-251">Int16</span></span>|  
|<span data-ttu-id="6649e-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6649e-252">DESCRIPTION</span></span>|<span data-ttu-id="6649e-253">String</span><span class="sxs-lookup"><span data-stu-id="6649e-253">String</span></span>|  
|<span data-ttu-id="6649e-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-254">TYPE_NAME</span></span>|<span data-ttu-id="6649e-255">String</span><span class="sxs-lookup"><span data-stu-id="6649e-255">String</span></span>|  
|<span data-ttu-id="6649e-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="6649e-257">String</span><span class="sxs-lookup"><span data-stu-id="6649e-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="6649e-258">Catálogo</span><span class="sxs-lookup"><span data-stu-id="6649e-258">Catalog</span></span>  
  
|<span data-ttu-id="6649e-259">ColumName</span><span class="sxs-lookup"><span data-stu-id="6649e-259">ColumnName</span></span>|<span data-ttu-id="6649e-260">DataType</span><span class="sxs-lookup"><span data-stu-id="6649e-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6649e-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-261">CATALOG_NAME</span></span>|<span data-ttu-id="6649e-262">String</span><span class="sxs-lookup"><span data-stu-id="6649e-262">String</span></span>|  
|<span data-ttu-id="6649e-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6649e-263">DESCRIPTION</span></span>|<span data-ttu-id="6649e-264">String</span><span class="sxs-lookup"><span data-stu-id="6649e-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="6649e-265">Índices</span><span class="sxs-lookup"><span data-stu-id="6649e-265">Indexes</span></span>  
  
|<span data-ttu-id="6649e-266">ColumName</span><span class="sxs-lookup"><span data-stu-id="6649e-266">ColumnName</span></span>|<span data-ttu-id="6649e-267">DataType</span><span class="sxs-lookup"><span data-stu-id="6649e-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6649e-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-268">TABLE_CATALOG</span></span>|<span data-ttu-id="6649e-269">String</span><span class="sxs-lookup"><span data-stu-id="6649e-269">String</span></span>|  
|<span data-ttu-id="6649e-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="6649e-271">String</span><span class="sxs-lookup"><span data-stu-id="6649e-271">String</span></span>|  
|<span data-ttu-id="6649e-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-272">TABLE_NAME</span></span>|<span data-ttu-id="6649e-273">String</span><span class="sxs-lookup"><span data-stu-id="6649e-273">String</span></span>|  
|<span data-ttu-id="6649e-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-274">INDEX_CATALOG</span></span>|<span data-ttu-id="6649e-275">String</span><span class="sxs-lookup"><span data-stu-id="6649e-275">String</span></span>|  
|<span data-ttu-id="6649e-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="6649e-277">String</span><span class="sxs-lookup"><span data-stu-id="6649e-277">String</span></span>|  
|<span data-ttu-id="6649e-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-278">INDEX_NAME</span></span>|<span data-ttu-id="6649e-279">String</span><span class="sxs-lookup"><span data-stu-id="6649e-279">String</span></span>|  
|<span data-ttu-id="6649e-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="6649e-280">PRIMARY_KEY</span></span>|<span data-ttu-id="6649e-281">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-281">Boolean</span></span>|  
|<span data-ttu-id="6649e-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="6649e-282">UNIQUE</span></span>|<span data-ttu-id="6649e-283">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-283">Boolean</span></span>|  
|<span data-ttu-id="6649e-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="6649e-284">CLUSTERED</span></span>|<span data-ttu-id="6649e-285">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-285">Boolean</span></span>|  
|<span data-ttu-id="6649e-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="6649e-286">TYPE</span></span>|<span data-ttu-id="6649e-287">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-287">Int32</span></span>|  
|<span data-ttu-id="6649e-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="6649e-288">FILL_FACTOR</span></span>|<span data-ttu-id="6649e-289">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-289">Int32</span></span>|  
|<span data-ttu-id="6649e-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="6649e-290">INITIAL_SIZE</span></span>|<span data-ttu-id="6649e-291">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-291">Int32</span></span>|  
|<span data-ttu-id="6649e-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="6649e-292">NULLS</span></span>|<span data-ttu-id="6649e-293">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-293">Int32</span></span>|  
|<span data-ttu-id="6649e-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="6649e-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="6649e-295">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-295">Boolean</span></span>|  
|<span data-ttu-id="6649e-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="6649e-296">AUTO_UPDATE</span></span>|<span data-ttu-id="6649e-297">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-297">Boolean</span></span>|  
|<span data-ttu-id="6649e-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="6649e-298">NULL_COLLATION</span></span>|<span data-ttu-id="6649e-299">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-299">Int32</span></span>|  
|<span data-ttu-id="6649e-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6649e-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="6649e-301">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-301">Int64</span></span>|  
|<span data-ttu-id="6649e-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-302">COLUMN_NAME</span></span>|<span data-ttu-id="6649e-303">String</span><span class="sxs-lookup"><span data-stu-id="6649e-303">String</span></span>|  
|<span data-ttu-id="6649e-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-304">COLUMN_GUID</span></span>|<span data-ttu-id="6649e-305">GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-305">Guid</span></span>|  
|<span data-ttu-id="6649e-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="6649e-306">COLUMN_PROPID</span></span>|<span data-ttu-id="6649e-307">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-307">Int64</span></span>|  
|<span data-ttu-id="6649e-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="6649e-308">COLLATION</span></span>|<span data-ttu-id="6649e-309">Int16</span><span class="sxs-lookup"><span data-stu-id="6649e-309">Int16</span></span>|  
|<span data-ttu-id="6649e-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="6649e-310">CARDINALITY</span></span>|<span data-ttu-id="6649e-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="6649e-311">Decimal</span></span>|  
|<span data-ttu-id="6649e-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="6649e-312">PAGES</span></span>|<span data-ttu-id="6649e-313">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-313">Int32</span></span>|  
|<span data-ttu-id="6649e-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="6649e-314">FILTER_CONDITION</span></span>|<span data-ttu-id="6649e-315">String</span><span class="sxs-lookup"><span data-stu-id="6649e-315">String</span></span>|  
|<span data-ttu-id="6649e-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="6649e-316">INTEGRATED</span></span>|<span data-ttu-id="6649e-317">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="6649e-318">Proveedor OLE DB de Microsoft para Oracle</span><span class="sxs-lookup"><span data-stu-id="6649e-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="6649e-319">El controlador OLE DB de Microsoft para Oracle admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="6649e-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="6649e-320">Tablas</span><span class="sxs-lookup"><span data-stu-id="6649e-320">Tables</span></span>  
  
- <span data-ttu-id="6649e-321">Columnas</span><span class="sxs-lookup"><span data-stu-id="6649e-321">Columns</span></span>  
  
- <span data-ttu-id="6649e-322">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="6649e-322">Procedures</span></span>  
  
- <span data-ttu-id="6649e-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="6649e-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="6649e-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="6649e-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="6649e-325">Vistas</span><span class="sxs-lookup"><span data-stu-id="6649e-325">Views</span></span>  
  
- <span data-ttu-id="6649e-326">Índices</span><span class="sxs-lookup"><span data-stu-id="6649e-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="6649e-327">Tablas</span><span class="sxs-lookup"><span data-stu-id="6649e-327">Tables</span></span>  
  
|<span data-ttu-id="6649e-328">ColumName</span><span class="sxs-lookup"><span data-stu-id="6649e-328">ColumnName</span></span>|<span data-ttu-id="6649e-329">DataType</span><span class="sxs-lookup"><span data-stu-id="6649e-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6649e-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-330">TABLE_CATALOG</span></span>|<span data-ttu-id="6649e-331">String</span><span class="sxs-lookup"><span data-stu-id="6649e-331">String</span></span>|  
|<span data-ttu-id="6649e-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="6649e-333">String</span><span class="sxs-lookup"><span data-stu-id="6649e-333">String</span></span>|  
|<span data-ttu-id="6649e-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-334">TABLE_NAME</span></span>|<span data-ttu-id="6649e-335">String</span><span class="sxs-lookup"><span data-stu-id="6649e-335">String</span></span>|  
|<span data-ttu-id="6649e-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="6649e-336">TABLE_TYPE</span></span>|<span data-ttu-id="6649e-337">String</span><span class="sxs-lookup"><span data-stu-id="6649e-337">String</span></span>|  
|<span data-ttu-id="6649e-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-338">TABLE_GUID</span></span>|<span data-ttu-id="6649e-339">GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-339">Guid</span></span>|  
|<span data-ttu-id="6649e-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6649e-340">DESCRIPTION</span></span>|<span data-ttu-id="6649e-341">String</span><span class="sxs-lookup"><span data-stu-id="6649e-341">String</span></span>|  
|<span data-ttu-id="6649e-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="6649e-342">TABLE_PROPID</span></span>|<span data-ttu-id="6649e-343">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-343">Int64</span></span>|  
|<span data-ttu-id="6649e-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="6649e-344">DATE_CREATED</span></span>|<span data-ttu-id="6649e-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="6649e-345">DateTime</span></span>|  
|<span data-ttu-id="6649e-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="6649e-346">DATE_MODIFIED</span></span>|<span data-ttu-id="6649e-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="6649e-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="6649e-348">Columnas</span><span class="sxs-lookup"><span data-stu-id="6649e-348">Columns</span></span>  
  
|<span data-ttu-id="6649e-349">ColumName</span><span class="sxs-lookup"><span data-stu-id="6649e-349">ColumnName</span></span>|<span data-ttu-id="6649e-350">DataType</span><span class="sxs-lookup"><span data-stu-id="6649e-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6649e-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-351">TABLE_CATALOG</span></span>|<span data-ttu-id="6649e-352">String</span><span class="sxs-lookup"><span data-stu-id="6649e-352">String</span></span>|  
|<span data-ttu-id="6649e-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="6649e-354">String</span><span class="sxs-lookup"><span data-stu-id="6649e-354">String</span></span>|  
|<span data-ttu-id="6649e-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-355">TABLE_NAME</span></span>|<span data-ttu-id="6649e-356">String</span><span class="sxs-lookup"><span data-stu-id="6649e-356">String</span></span>|  
|<span data-ttu-id="6649e-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-357">COLUMN_NAME</span></span>|<span data-ttu-id="6649e-358">String</span><span class="sxs-lookup"><span data-stu-id="6649e-358">String</span></span>|  
|<span data-ttu-id="6649e-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-359">COLUMN_GUID</span></span>|<span data-ttu-id="6649e-360">GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-360">Guid</span></span>|  
|<span data-ttu-id="6649e-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="6649e-361">COLUMN_PROPID</span></span>|<span data-ttu-id="6649e-362">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-362">Int64</span></span>|  
|<span data-ttu-id="6649e-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6649e-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="6649e-364">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-364">Int64</span></span>|  
|<span data-ttu-id="6649e-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="6649e-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="6649e-366">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-366">Boolean</span></span>|  
|<span data-ttu-id="6649e-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="6649e-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="6649e-368">String</span><span class="sxs-lookup"><span data-stu-id="6649e-368">String</span></span>|  
|<span data-ttu-id="6649e-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="6649e-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="6649e-370">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-370">Int64</span></span>|  
|<span data-ttu-id="6649e-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6649e-371">IS_NULLABLE</span></span>|<span data-ttu-id="6649e-372">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-372">Boolean</span></span>|  
|<span data-ttu-id="6649e-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6649e-373">DATA_TYPE</span></span>|<span data-ttu-id="6649e-374">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-374">Int32</span></span>|  
|<span data-ttu-id="6649e-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-375">TYPE_GUID</span></span>|<span data-ttu-id="6649e-376">GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-376">Guid</span></span>|  
|<span data-ttu-id="6649e-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6649e-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="6649e-378">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-378">Int64</span></span>|  
|<span data-ttu-id="6649e-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6649e-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="6649e-380">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-380">Int64</span></span>|  
|<span data-ttu-id="6649e-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="6649e-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="6649e-382">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-382">Int32</span></span>|  
|<span data-ttu-id="6649e-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="6649e-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="6649e-384">Int16</span><span class="sxs-lookup"><span data-stu-id="6649e-384">Int16</span></span>|  
|<span data-ttu-id="6649e-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="6649e-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="6649e-386">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-386">Int64</span></span>|  
|<span data-ttu-id="6649e-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="6649e-388">String</span><span class="sxs-lookup"><span data-stu-id="6649e-388">String</span></span>|  
|<span data-ttu-id="6649e-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="6649e-390">String</span><span class="sxs-lookup"><span data-stu-id="6649e-390">String</span></span>|  
|<span data-ttu-id="6649e-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="6649e-392">String</span><span class="sxs-lookup"><span data-stu-id="6649e-392">String</span></span>|  
|<span data-ttu-id="6649e-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="6649e-394">String</span><span class="sxs-lookup"><span data-stu-id="6649e-394">String</span></span>|  
|<span data-ttu-id="6649e-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="6649e-396">String</span><span class="sxs-lookup"><span data-stu-id="6649e-396">String</span></span>|  
|<span data-ttu-id="6649e-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-397">COLLATION_NAME</span></span>|<span data-ttu-id="6649e-398">String</span><span class="sxs-lookup"><span data-stu-id="6649e-398">String</span></span>|  
|<span data-ttu-id="6649e-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="6649e-400">String</span><span class="sxs-lookup"><span data-stu-id="6649e-400">String</span></span>|  
|<span data-ttu-id="6649e-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="6649e-402">String</span><span class="sxs-lookup"><span data-stu-id="6649e-402">String</span></span>|  
|<span data-ttu-id="6649e-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-403">DOMAIN_NAME</span></span>|<span data-ttu-id="6649e-404">String</span><span class="sxs-lookup"><span data-stu-id="6649e-404">String</span></span>|  
|<span data-ttu-id="6649e-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6649e-405">DESCRIPTION</span></span>|<span data-ttu-id="6649e-406">String</span><span class="sxs-lookup"><span data-stu-id="6649e-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="6649e-407">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="6649e-407">Procedures</span></span>  
  
|<span data-ttu-id="6649e-408">ColumName</span><span class="sxs-lookup"><span data-stu-id="6649e-408">ColumnName</span></span>|<span data-ttu-id="6649e-409">DataType</span><span class="sxs-lookup"><span data-stu-id="6649e-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6649e-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="6649e-411">String</span><span class="sxs-lookup"><span data-stu-id="6649e-411">String</span></span>|  
|<span data-ttu-id="6649e-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="6649e-413">String</span><span class="sxs-lookup"><span data-stu-id="6649e-413">String</span></span>|  
|<span data-ttu-id="6649e-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="6649e-415">String</span><span class="sxs-lookup"><span data-stu-id="6649e-415">String</span></span>|  
|<span data-ttu-id="6649e-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="6649e-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="6649e-417">Int16</span><span class="sxs-lookup"><span data-stu-id="6649e-417">Int16</span></span>|  
|<span data-ttu-id="6649e-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="6649e-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="6649e-419">String</span><span class="sxs-lookup"><span data-stu-id="6649e-419">String</span></span>|  
|<span data-ttu-id="6649e-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6649e-420">DESCRIPTION</span></span>|<span data-ttu-id="6649e-421">String</span><span class="sxs-lookup"><span data-stu-id="6649e-421">String</span></span>|  
|<span data-ttu-id="6649e-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="6649e-422">DATE_CREATED</span></span>|<span data-ttu-id="6649e-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="6649e-423">DateTime</span></span>|  
|<span data-ttu-id="6649e-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="6649e-424">DATE_MODIFIED</span></span>|<span data-ttu-id="6649e-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="6649e-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="6649e-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="6649e-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="6649e-427">ColumName</span><span class="sxs-lookup"><span data-stu-id="6649e-427">ColumnName</span></span>|<span data-ttu-id="6649e-428">DataType</span><span class="sxs-lookup"><span data-stu-id="6649e-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6649e-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="6649e-430">String</span><span class="sxs-lookup"><span data-stu-id="6649e-430">String</span></span>|  
|<span data-ttu-id="6649e-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="6649e-432">String</span><span class="sxs-lookup"><span data-stu-id="6649e-432">String</span></span>|  
|<span data-ttu-id="6649e-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="6649e-434">String</span><span class="sxs-lookup"><span data-stu-id="6649e-434">String</span></span>|  
|<span data-ttu-id="6649e-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-435">COLUMN_NAME</span></span>|<span data-ttu-id="6649e-436">String</span><span class="sxs-lookup"><span data-stu-id="6649e-436">String</span></span>|  
|<span data-ttu-id="6649e-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-437">COLUMN_GUID</span></span>|<span data-ttu-id="6649e-438">GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-438">Guid</span></span>|  
|<span data-ttu-id="6649e-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="6649e-439">COLUMN_PROPID</span></span>|<span data-ttu-id="6649e-440">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-440">Int64</span></span>|  
|<span data-ttu-id="6649e-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="6649e-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="6649e-442">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-442">Int64</span></span>|  
|<span data-ttu-id="6649e-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6649e-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="6649e-444">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-444">Int64</span></span>|  
|<span data-ttu-id="6649e-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6649e-445">IS_NULLABLE</span></span>|<span data-ttu-id="6649e-446">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-446">Boolean</span></span>|  
|<span data-ttu-id="6649e-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6649e-447">DATA_TYPE</span></span>|<span data-ttu-id="6649e-448">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-448">Int32</span></span>|  
|<span data-ttu-id="6649e-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-449">TYPE_GUID</span></span>|<span data-ttu-id="6649e-450">GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-450">Guid</span></span>|  
|<span data-ttu-id="6649e-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6649e-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="6649e-452">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-452">Int64</span></span>|  
|<span data-ttu-id="6649e-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6649e-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="6649e-454">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-454">Int64</span></span>|  
|<span data-ttu-id="6649e-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="6649e-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="6649e-456">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-456">Int32</span></span>|  
|<span data-ttu-id="6649e-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="6649e-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="6649e-458">Int16</span><span class="sxs-lookup"><span data-stu-id="6649e-458">Int16</span></span>|  
|<span data-ttu-id="6649e-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6649e-459">DESCRIPTION</span></span>|<span data-ttu-id="6649e-460">String</span><span class="sxs-lookup"><span data-stu-id="6649e-460">String</span></span>|  
|<span data-ttu-id="6649e-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="6649e-461">OVERLOAD</span></span>|<span data-ttu-id="6649e-462">Int16</span><span class="sxs-lookup"><span data-stu-id="6649e-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="6649e-463">Vistas</span><span class="sxs-lookup"><span data-stu-id="6649e-463">Views</span></span>  
  
|<span data-ttu-id="6649e-464">ColumName</span><span class="sxs-lookup"><span data-stu-id="6649e-464">ColumnName</span></span>|<span data-ttu-id="6649e-465">DataType</span><span class="sxs-lookup"><span data-stu-id="6649e-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6649e-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-466">TABLE_CATALOG</span></span>|<span data-ttu-id="6649e-467">String</span><span class="sxs-lookup"><span data-stu-id="6649e-467">String</span></span>|  
|<span data-ttu-id="6649e-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="6649e-469">String</span><span class="sxs-lookup"><span data-stu-id="6649e-469">String</span></span>|  
|<span data-ttu-id="6649e-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-470">TABLE_NAME</span></span>|<span data-ttu-id="6649e-471">String</span><span class="sxs-lookup"><span data-stu-id="6649e-471">String</span></span>|  
|<span data-ttu-id="6649e-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="6649e-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="6649e-473">String</span><span class="sxs-lookup"><span data-stu-id="6649e-473">String</span></span>|  
|<span data-ttu-id="6649e-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="6649e-474">CHECK_OPTION</span></span>|<span data-ttu-id="6649e-475">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-475">Boolean</span></span>|  
|<span data-ttu-id="6649e-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="6649e-476">IS_UPDATABLE</span></span>|<span data-ttu-id="6649e-477">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-477">Boolean</span></span>|  
|<span data-ttu-id="6649e-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6649e-478">DESCRIPTION</span></span>|<span data-ttu-id="6649e-479">String</span><span class="sxs-lookup"><span data-stu-id="6649e-479">String</span></span>|  
|<span data-ttu-id="6649e-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="6649e-480">DATE_CREATED</span></span>|<span data-ttu-id="6649e-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="6649e-481">DateTime</span></span>|  
|<span data-ttu-id="6649e-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="6649e-482">DATE_MODIFIED</span></span>|<span data-ttu-id="6649e-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="6649e-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="6649e-484">Índices</span><span class="sxs-lookup"><span data-stu-id="6649e-484">Indexes</span></span>  
  
|<span data-ttu-id="6649e-485">ColumName</span><span class="sxs-lookup"><span data-stu-id="6649e-485">ColumnName</span></span>|<span data-ttu-id="6649e-486">DataType</span><span class="sxs-lookup"><span data-stu-id="6649e-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6649e-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-487">TABLE_CATALOG</span></span>|<span data-ttu-id="6649e-488">String</span><span class="sxs-lookup"><span data-stu-id="6649e-488">String</span></span>|  
|<span data-ttu-id="6649e-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="6649e-490">String</span><span class="sxs-lookup"><span data-stu-id="6649e-490">String</span></span>|  
|<span data-ttu-id="6649e-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-491">TABLE_NAME</span></span>|<span data-ttu-id="6649e-492">String</span><span class="sxs-lookup"><span data-stu-id="6649e-492">String</span></span>|  
|<span data-ttu-id="6649e-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-493">INDEX_CATALOG</span></span>|<span data-ttu-id="6649e-494">String</span><span class="sxs-lookup"><span data-stu-id="6649e-494">String</span></span>|  
|<span data-ttu-id="6649e-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="6649e-496">String</span><span class="sxs-lookup"><span data-stu-id="6649e-496">String</span></span>|  
|<span data-ttu-id="6649e-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-497">INDEX_NAME</span></span>|<span data-ttu-id="6649e-498">String</span><span class="sxs-lookup"><span data-stu-id="6649e-498">String</span></span>|  
|<span data-ttu-id="6649e-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="6649e-499">PRIMARY_KEY</span></span>|<span data-ttu-id="6649e-500">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-500">Boolean</span></span>|  
|<span data-ttu-id="6649e-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="6649e-501">UNIQUE</span></span>|<span data-ttu-id="6649e-502">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-502">Boolean</span></span>|  
|<span data-ttu-id="6649e-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="6649e-503">CLUSTERED</span></span>|<span data-ttu-id="6649e-504">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-504">Boolean</span></span>|  
|<span data-ttu-id="6649e-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="6649e-505">TYPE</span></span>|<span data-ttu-id="6649e-506">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-506">Int32</span></span>|  
|<span data-ttu-id="6649e-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="6649e-507">FILL_FACTOR</span></span>|<span data-ttu-id="6649e-508">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-508">Int32</span></span>|  
|<span data-ttu-id="6649e-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="6649e-509">INITIAL_SIZE</span></span>|<span data-ttu-id="6649e-510">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-510">Int32</span></span>|  
|<span data-ttu-id="6649e-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="6649e-511">NULLS</span></span>|<span data-ttu-id="6649e-512">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-512">Int32</span></span>|  
|<span data-ttu-id="6649e-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="6649e-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="6649e-514">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-514">Boolean</span></span>|  
|<span data-ttu-id="6649e-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="6649e-515">AUTO_UPDATE</span></span>|<span data-ttu-id="6649e-516">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-516">Boolean</span></span>|  
|<span data-ttu-id="6649e-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="6649e-517">NULL_COLLATION</span></span>|<span data-ttu-id="6649e-518">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-518">Int32</span></span>|  
|<span data-ttu-id="6649e-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6649e-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="6649e-520">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-520">Int64</span></span>|  
|<span data-ttu-id="6649e-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-521">COLUMN_NAME</span></span>|<span data-ttu-id="6649e-522">String</span><span class="sxs-lookup"><span data-stu-id="6649e-522">String</span></span>|  
|<span data-ttu-id="6649e-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-523">COLUMN_GUID</span></span>|<span data-ttu-id="6649e-524">GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-524">Guid</span></span>|  
|<span data-ttu-id="6649e-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="6649e-525">COLUMN_PROPID</span></span>|<span data-ttu-id="6649e-526">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-526">Int64</span></span>|  
|<span data-ttu-id="6649e-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="6649e-527">COLLATION</span></span>|<span data-ttu-id="6649e-528">Int16</span><span class="sxs-lookup"><span data-stu-id="6649e-528">Int16</span></span>|  
|<span data-ttu-id="6649e-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="6649e-529">CARDINALITY</span></span>|<span data-ttu-id="6649e-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="6649e-530">Decimal</span></span>|  
|<span data-ttu-id="6649e-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="6649e-531">PAGES</span></span>|<span data-ttu-id="6649e-532">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-532">Int32</span></span>|  
|<span data-ttu-id="6649e-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="6649e-533">FILTER_CONDITION</span></span>|<span data-ttu-id="6649e-534">String</span><span class="sxs-lookup"><span data-stu-id="6649e-534">String</span></span>|  
|<span data-ttu-id="6649e-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="6649e-535">INTEGRATED</span></span>|<span data-ttu-id="6649e-536">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="6649e-537">Proveedor OLE DB de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="6649e-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="6649e-538">El controlador OLE DB de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="6649e-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="6649e-539">Tablas</span><span class="sxs-lookup"><span data-stu-id="6649e-539">Tables</span></span>  
  
- <span data-ttu-id="6649e-540">Columnas</span><span class="sxs-lookup"><span data-stu-id="6649e-540">Columns</span></span>  
  
- <span data-ttu-id="6649e-541">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="6649e-541">Procedures</span></span>  
  
- <span data-ttu-id="6649e-542">Vistas</span><span class="sxs-lookup"><span data-stu-id="6649e-542">Views</span></span>  
  
- <span data-ttu-id="6649e-543">Índices</span><span class="sxs-lookup"><span data-stu-id="6649e-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="6649e-544">Tablas</span><span class="sxs-lookup"><span data-stu-id="6649e-544">Tables</span></span>  
  
|<span data-ttu-id="6649e-545">ColumName</span><span class="sxs-lookup"><span data-stu-id="6649e-545">ColumnName</span></span>|<span data-ttu-id="6649e-546">DataType</span><span class="sxs-lookup"><span data-stu-id="6649e-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6649e-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-547">TABLE_CATALOG</span></span>|<span data-ttu-id="6649e-548">String</span><span class="sxs-lookup"><span data-stu-id="6649e-548">String</span></span>|  
|<span data-ttu-id="6649e-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="6649e-550">String</span><span class="sxs-lookup"><span data-stu-id="6649e-550">String</span></span>|  
|<span data-ttu-id="6649e-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-551">TABLE_NAME</span></span>|<span data-ttu-id="6649e-552">String</span><span class="sxs-lookup"><span data-stu-id="6649e-552">String</span></span>|  
|<span data-ttu-id="6649e-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="6649e-553">TABLE_TYPE</span></span>|<span data-ttu-id="6649e-554">String</span><span class="sxs-lookup"><span data-stu-id="6649e-554">String</span></span>|  
|<span data-ttu-id="6649e-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-555">TABLE_GUID</span></span>|<span data-ttu-id="6649e-556">GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-556">Guid</span></span>|  
|<span data-ttu-id="6649e-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6649e-557">DESCRIPTION</span></span>|<span data-ttu-id="6649e-558">String</span><span class="sxs-lookup"><span data-stu-id="6649e-558">String</span></span>|  
|<span data-ttu-id="6649e-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="6649e-559">TABLE_PROPID</span></span>|<span data-ttu-id="6649e-560">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-560">Int64</span></span>|  
|<span data-ttu-id="6649e-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="6649e-561">DATE_CREATED</span></span>|<span data-ttu-id="6649e-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="6649e-562">DateTime</span></span>|  
|<span data-ttu-id="6649e-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="6649e-563">DATE_MODIFIED</span></span>|<span data-ttu-id="6649e-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="6649e-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="6649e-565">Columnas</span><span class="sxs-lookup"><span data-stu-id="6649e-565">Columns</span></span>  
  
|<span data-ttu-id="6649e-566">ColumName</span><span class="sxs-lookup"><span data-stu-id="6649e-566">ColumnName</span></span>|<span data-ttu-id="6649e-567">DataType</span><span class="sxs-lookup"><span data-stu-id="6649e-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6649e-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-568">TABLE_CATALOG</span></span>|<span data-ttu-id="6649e-569">String</span><span class="sxs-lookup"><span data-stu-id="6649e-569">String</span></span>|  
|<span data-ttu-id="6649e-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="6649e-571">String</span><span class="sxs-lookup"><span data-stu-id="6649e-571">String</span></span>|  
|<span data-ttu-id="6649e-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-572">TABLE_NAME</span></span>|<span data-ttu-id="6649e-573">String</span><span class="sxs-lookup"><span data-stu-id="6649e-573">String</span></span>|  
|<span data-ttu-id="6649e-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-574">COLUMN_NAME</span></span>|<span data-ttu-id="6649e-575">String</span><span class="sxs-lookup"><span data-stu-id="6649e-575">String</span></span>|  
|<span data-ttu-id="6649e-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-576">COLUMN_GUID</span></span>|<span data-ttu-id="6649e-577">GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-577">Guid</span></span>|  
|<span data-ttu-id="6649e-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="6649e-578">COLUMN_PROPID</span></span>|<span data-ttu-id="6649e-579">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-579">Int64</span></span>|  
|<span data-ttu-id="6649e-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6649e-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="6649e-581">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-581">Int64</span></span>|  
|<span data-ttu-id="6649e-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="6649e-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="6649e-583">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-583">Boolean</span></span>|  
|<span data-ttu-id="6649e-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="6649e-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="6649e-585">String</span><span class="sxs-lookup"><span data-stu-id="6649e-585">String</span></span>|  
|<span data-ttu-id="6649e-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="6649e-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="6649e-587">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-587">Int64</span></span>|  
|<span data-ttu-id="6649e-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6649e-588">IS_NULLABLE</span></span>|<span data-ttu-id="6649e-589">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-589">Boolean</span></span>|  
|<span data-ttu-id="6649e-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6649e-590">DATA_TYPE</span></span>|<span data-ttu-id="6649e-591">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-591">Int32</span></span>|  
|<span data-ttu-id="6649e-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-592">TYPE_GUID</span></span>|<span data-ttu-id="6649e-593">GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-593">Guid</span></span>|  
|<span data-ttu-id="6649e-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6649e-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="6649e-595">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-595">Int64</span></span>|  
|<span data-ttu-id="6649e-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6649e-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="6649e-597">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-597">Int64</span></span>|  
|<span data-ttu-id="6649e-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="6649e-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="6649e-599">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-599">Int32</span></span>|  
|<span data-ttu-id="6649e-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="6649e-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="6649e-601">Int16</span><span class="sxs-lookup"><span data-stu-id="6649e-601">Int16</span></span>|  
|<span data-ttu-id="6649e-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="6649e-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="6649e-603">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-603">Int64</span></span>|  
|<span data-ttu-id="6649e-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="6649e-605">String</span><span class="sxs-lookup"><span data-stu-id="6649e-605">String</span></span>|  
|<span data-ttu-id="6649e-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="6649e-607">String</span><span class="sxs-lookup"><span data-stu-id="6649e-607">String</span></span>|  
|<span data-ttu-id="6649e-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="6649e-609">String</span><span class="sxs-lookup"><span data-stu-id="6649e-609">String</span></span>|  
|<span data-ttu-id="6649e-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="6649e-611">String</span><span class="sxs-lookup"><span data-stu-id="6649e-611">String</span></span>|  
|<span data-ttu-id="6649e-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="6649e-613">String</span><span class="sxs-lookup"><span data-stu-id="6649e-613">String</span></span>|  
|<span data-ttu-id="6649e-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-614">COLLATION_NAME</span></span>|<span data-ttu-id="6649e-615">String</span><span class="sxs-lookup"><span data-stu-id="6649e-615">String</span></span>|  
|<span data-ttu-id="6649e-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="6649e-617">String</span><span class="sxs-lookup"><span data-stu-id="6649e-617">String</span></span>|  
|<span data-ttu-id="6649e-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="6649e-619">String</span><span class="sxs-lookup"><span data-stu-id="6649e-619">String</span></span>|  
|<span data-ttu-id="6649e-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-620">DOMAIN_NAME</span></span>|<span data-ttu-id="6649e-621">String</span><span class="sxs-lookup"><span data-stu-id="6649e-621">String</span></span>|  
|<span data-ttu-id="6649e-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6649e-622">DESCRIPTION</span></span>|<span data-ttu-id="6649e-623">String</span><span class="sxs-lookup"><span data-stu-id="6649e-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="6649e-624">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="6649e-624">Procedures</span></span>  
  
|<span data-ttu-id="6649e-625">ColumName</span><span class="sxs-lookup"><span data-stu-id="6649e-625">ColumnName</span></span>|<span data-ttu-id="6649e-626">DataType</span><span class="sxs-lookup"><span data-stu-id="6649e-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6649e-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="6649e-628">String</span><span class="sxs-lookup"><span data-stu-id="6649e-628">String</span></span>|  
|<span data-ttu-id="6649e-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="6649e-630">String</span><span class="sxs-lookup"><span data-stu-id="6649e-630">String</span></span>|  
|<span data-ttu-id="6649e-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="6649e-632">String</span><span class="sxs-lookup"><span data-stu-id="6649e-632">String</span></span>|  
|<span data-ttu-id="6649e-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="6649e-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="6649e-634">Int16</span><span class="sxs-lookup"><span data-stu-id="6649e-634">Int16</span></span>|  
|<span data-ttu-id="6649e-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="6649e-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="6649e-636">String</span><span class="sxs-lookup"><span data-stu-id="6649e-636">String</span></span>|  
|<span data-ttu-id="6649e-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6649e-637">DESCRIPTION</span></span>|<span data-ttu-id="6649e-638">String</span><span class="sxs-lookup"><span data-stu-id="6649e-638">String</span></span>|  
|<span data-ttu-id="6649e-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="6649e-639">DATE_CREATED</span></span>|<span data-ttu-id="6649e-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="6649e-640">DateTime</span></span>|  
|<span data-ttu-id="6649e-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="6649e-641">DATE_MODIFIED</span></span>|<span data-ttu-id="6649e-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="6649e-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="6649e-643">Vistas</span><span class="sxs-lookup"><span data-stu-id="6649e-643">Views</span></span>  
  
|<span data-ttu-id="6649e-644">ColumName</span><span class="sxs-lookup"><span data-stu-id="6649e-644">ColumnName</span></span>|<span data-ttu-id="6649e-645">DataType</span><span class="sxs-lookup"><span data-stu-id="6649e-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6649e-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-646">TABLE_CATALOG</span></span>|<span data-ttu-id="6649e-647">String</span><span class="sxs-lookup"><span data-stu-id="6649e-647">String</span></span>|  
|<span data-ttu-id="6649e-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="6649e-649">String</span><span class="sxs-lookup"><span data-stu-id="6649e-649">String</span></span>|  
|<span data-ttu-id="6649e-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-650">TABLE_NAME</span></span>|<span data-ttu-id="6649e-651">String</span><span class="sxs-lookup"><span data-stu-id="6649e-651">String</span></span>|  
|<span data-ttu-id="6649e-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="6649e-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="6649e-653">String</span><span class="sxs-lookup"><span data-stu-id="6649e-653">String</span></span>|  
|<span data-ttu-id="6649e-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="6649e-654">CHECK_OPTION</span></span>|<span data-ttu-id="6649e-655">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-655">Boolean</span></span>|  
|<span data-ttu-id="6649e-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="6649e-656">IS_UPDATABLE</span></span>|<span data-ttu-id="6649e-657">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-657">Boolean</span></span>|  
|<span data-ttu-id="6649e-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6649e-658">DESCRIPTION</span></span>|<span data-ttu-id="6649e-659">String</span><span class="sxs-lookup"><span data-stu-id="6649e-659">String</span></span>|  
|<span data-ttu-id="6649e-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="6649e-660">DATE_CREATED</span></span>|<span data-ttu-id="6649e-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="6649e-661">DateTime</span></span>|  
|<span data-ttu-id="6649e-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="6649e-662">DATE_MODIFIED</span></span>|<span data-ttu-id="6649e-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="6649e-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="6649e-664">Índices</span><span class="sxs-lookup"><span data-stu-id="6649e-664">Indexes</span></span>  
  
|<span data-ttu-id="6649e-665">ColumName</span><span class="sxs-lookup"><span data-stu-id="6649e-665">ColumnName</span></span>|<span data-ttu-id="6649e-666">DataType</span><span class="sxs-lookup"><span data-stu-id="6649e-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6649e-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-667">TABLE_CATALOG</span></span>|<span data-ttu-id="6649e-668">String</span><span class="sxs-lookup"><span data-stu-id="6649e-668">String</span></span>|  
|<span data-ttu-id="6649e-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="6649e-670">String</span><span class="sxs-lookup"><span data-stu-id="6649e-670">String</span></span>|  
|<span data-ttu-id="6649e-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-671">TABLE_NAME</span></span>|<span data-ttu-id="6649e-672">String</span><span class="sxs-lookup"><span data-stu-id="6649e-672">String</span></span>|  
|<span data-ttu-id="6649e-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6649e-673">INDEX_CATALOG</span></span>|<span data-ttu-id="6649e-674">String</span><span class="sxs-lookup"><span data-stu-id="6649e-674">String</span></span>|  
|<span data-ttu-id="6649e-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6649e-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="6649e-676">String</span><span class="sxs-lookup"><span data-stu-id="6649e-676">String</span></span>|  
|<span data-ttu-id="6649e-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-677">INDEX_NAME</span></span>|<span data-ttu-id="6649e-678">String</span><span class="sxs-lookup"><span data-stu-id="6649e-678">String</span></span>|  
|<span data-ttu-id="6649e-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="6649e-679">PRIMARY_KEY</span></span>|<span data-ttu-id="6649e-680">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-680">Boolean</span></span>|  
|<span data-ttu-id="6649e-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="6649e-681">UNIQUE</span></span>|<span data-ttu-id="6649e-682">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-682">Boolean</span></span>|  
|<span data-ttu-id="6649e-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="6649e-683">CLUSTERED</span></span>|<span data-ttu-id="6649e-684">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-684">Boolean</span></span>|  
|<span data-ttu-id="6649e-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="6649e-685">TYPE</span></span>|<span data-ttu-id="6649e-686">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-686">Int32</span></span>|  
|<span data-ttu-id="6649e-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="6649e-687">FILL_FACTOR</span></span>|<span data-ttu-id="6649e-688">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-688">Int32</span></span>|  
|<span data-ttu-id="6649e-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="6649e-689">INITIAL_SIZE</span></span>|<span data-ttu-id="6649e-690">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-690">Int32</span></span>|  
|<span data-ttu-id="6649e-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="6649e-691">NULLS</span></span>|<span data-ttu-id="6649e-692">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-692">Int32</span></span>|  
|<span data-ttu-id="6649e-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="6649e-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="6649e-694">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-694">Boolean</span></span>|  
|<span data-ttu-id="6649e-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="6649e-695">AUTO_UPDATE</span></span>|<span data-ttu-id="6649e-696">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-696">Boolean</span></span>|  
|<span data-ttu-id="6649e-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="6649e-697">NULL_COLLATION</span></span>|<span data-ttu-id="6649e-698">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-698">Int32</span></span>|  
|<span data-ttu-id="6649e-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6649e-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="6649e-700">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-700">Int64</span></span>|  
|<span data-ttu-id="6649e-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6649e-701">COLUMN_NAME</span></span>|<span data-ttu-id="6649e-702">String</span><span class="sxs-lookup"><span data-stu-id="6649e-702">String</span></span>|  
|<span data-ttu-id="6649e-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-703">COLUMN_GUID</span></span>|<span data-ttu-id="6649e-704">GUID</span><span class="sxs-lookup"><span data-stu-id="6649e-704">Guid</span></span>|  
|<span data-ttu-id="6649e-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="6649e-705">COLUMN_PROPID</span></span>|<span data-ttu-id="6649e-706">Int64</span><span class="sxs-lookup"><span data-stu-id="6649e-706">Int64</span></span>|  
|<span data-ttu-id="6649e-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="6649e-707">COLLATION</span></span>|<span data-ttu-id="6649e-708">Int16</span><span class="sxs-lookup"><span data-stu-id="6649e-708">Int16</span></span>|  
|<span data-ttu-id="6649e-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="6649e-709">CARDINALITY</span></span>|<span data-ttu-id="6649e-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="6649e-710">Decimal</span></span>|  
|<span data-ttu-id="6649e-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="6649e-711">PAGES</span></span>|<span data-ttu-id="6649e-712">Int32</span><span class="sxs-lookup"><span data-stu-id="6649e-712">Int32</span></span>|  
|<span data-ttu-id="6649e-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="6649e-713">FILTER_CONDITION</span></span>|<span data-ttu-id="6649e-714">String</span><span class="sxs-lookup"><span data-stu-id="6649e-714">String</span></span>|  
|<span data-ttu-id="6649e-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="6649e-715">INTEGRATED</span></span>|<span data-ttu-id="6649e-716">Booleano</span><span class="sxs-lookup"><span data-stu-id="6649e-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6649e-717">Vea también</span><span class="sxs-lookup"><span data-stu-id="6649e-717">See also</span></span>

- [<span data-ttu-id="6649e-718">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="6649e-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
