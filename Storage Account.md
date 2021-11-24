# Storage Account
- Blob, File share, Queue, Table, Disk 등 모든 Azure Storage 데이터 개체가 포함된다.
- HTTP 또는 HTTPS를 통해 전 세계 어디에서나 액세스할 수 있는 Azure Storage 데이터에 고유한 네임스페이스를 제공한다.
- 데이터는 지속적이고 가용성이 높으며 안전하고 대규모로 확장 가능하다.


## 1. Account Kind (계정 유형)
- StorageV2 (General purpose v2)
- Storage (General purpose v1)
- Block Blob Storage
- File Storage

## 2. Replication (중복)
### 2-1. LRS (Locally-redundant storage)
![Untitled (3)](https://user-images.githubusercontent.com/50107548/143176270-38b1774d-0266-4679-aeb7-794cd9ba7e7c.png)
- 데이터를 주 지역(Primary region) 내에서 동기적으로 세 번 복사한다.
- 간단하고 저렴하지만 다른 옵션에 비해 내구성이 가장 낮다.
- 단일 데이터 센터 내에 있기 때문에 서버 랙 및 드라이브 오류로부터 데이터 보호에는 용이하지만 데이터 센터 자체에 재해가 발생하는 경우 데이터가 손실되거나 복구할 수 없게 된다.

### 2-2. ZRS (Zone-redundant storage)
![Untitled (4)](https://user-images.githubusercontent.com/50107548/143176303-0440e244-4fa5-4933-bd1f-bca26151c526.png)
- 데이터를 주 지역(Primary region)에 있는 3개의 Azure 가용성 영역에서 동기적으로 복사한다.
- 하나의 가용성 영역을 사용할 수 없게 되는 경우에도 읽기 및 쓰기 작업에 모두 계속해서 액세스할 수 있으며 Azure에서 DNS 재지정과 같은 네트워킹 업데이트를 수행한다.
- 고가용성이 필요한 시나리오인 경우 사용 권장된다.
- 데이터를 일시적으로 사용할 수 없는 경우 탁월하고 낮은 대기 시간과 복원력을 제공한다. 하지만 여러 영역에 영구적으로 영향을 주는 지역 재해로부터 데이터를 보호하는 데에는 어려움이 있다.

### 2-3. GRS (Geo-redundant storage)
![Untitled (5)](https://user-images.githubusercontent.com/50107548/143176341-7a45574e-0c9b-4857-a288-f4098865ea21.png)
- 데이터는 주 지역에서 동기적으로 세 번 복사한 다음, 보조 지역에 비동기적으로 복사한다.
- 지역 간 중복도를 통해 지역 중단으로부터 보호한다.
- 보조 지역에 대한 읽기 액세스의 경우 RA-GRS(Read-access Geo-redundant storage)를 사용한다.

### 2-4. GZRS (Geo-zone-redundant storage)
![Untitled (6)](https://user-images.githubusercontent.com/50107548/143176372-9f652352-e3d0-4960-bafe-6371496b6c4b.png)
- 데이터는 주 지역의 3개의 Azure 가용성 영역에서 동기적으로 복사한 다음, 보조 지역에 LRS를 사용하여 비동기적으로 복사한다.
- 고가용성 및 최대 내구성이 모두 필요한 시나리오에 적합하다.
- 보조 지역에 대한 읽기 액세스의 경우 RA-GZRS(Read-access Geo-zone-redundant storage)를 사용한다.
