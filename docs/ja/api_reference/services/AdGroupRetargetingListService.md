# AdGroupRetargetingListService
AdGroupRetargetingListServiceでは、広告グループレベルでのターゲットリスト設定に関する情報の取得および追加・更新・削除を行います。

#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/V6.0/AdGroupRetargetingListService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/V6.0/AdGroupRetargetingListService?wsdl|

#### Namespace
http://ss.yahooapis.jp/V6

#### サービス概要
広告グループレベルでのターゲットリスト設定に関する情報の取得および追加・更新・削除を行います。

#### 操作
AdGroupRetargetingListServiceで提供される操作を説明します。

## get
広告グループレベルでのターゲットリスト設定に関する情報を取得します。

#### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [AdGroupRetargetingListSelector](../data/AdGroupRetargetingListSelector.md) | 操作の対象とする広告グループレベルでのターゲットリスト設定です。 | 

##### ＜リクエストサンプル＞
```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:get>
      <ns1:selector>
        <ns1:accountId>100000001</ns1:accountId>
        <ns1:campaignIds>100000002</ns1:campaignIds>
        <ns1:targetListIds>100000003</ns1:targetListIds>
        <ns1:adGroupIds>100000004</ns1:adGroupIds>
        <ns1:excludedType>INCLUDED</ns1:excludedType>
      </ns1:selector>
    </ns1:get>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupRetargetingListPage](../data/AdGroupRetargetingListPage.md) | 取得される広告グループレベルでのターゲットリスト設定のエントリーです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>AdGroupRetargetingListService</ns1:service>
      <ns1:remainingQuota>74939</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.7359</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getResponse>
      <ns1:rval>
        <ns1:totalNumEntries>2</ns1:totalNumEntries>
        <ns1:Page.Type>AdGroupRetargetingListPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupRetargetingList>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:campaignId>100000002</ns1:campaignId>
            <ns1:campaignName>SampleCampaign</ns1:campaignName>
            <ns1:adGroupId>100000003</ns1:adGroupId>
            <ns1:adGroupName>SampleAdGroup1</ns1:adGroupName>
            <ns1:criterionTargetList>
              <ns1:targetListId>100000005</ns1:targetListId>
              <ns1:targetListName>デフォルトリスト</ns1:targetListName>
            </ns1:criterionTargetList>
            <ns1:excludedType>EXCLUDED</ns1:excludedType>
            <ns1:targetAll>DEACTIVE</ns1:targetAll>
          </ns1:adGroupRetargetingList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupRetargetingList>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:campaignId>100000002</ns1:campaignId>
            <ns1:campaignName>SampleCampaign</ns1:campaignName>
            <ns1:adGroupId>100000004</ns1:adGroupId>
            <ns1:adGroupName>SampleAdGroup2</ns1:adGroupName>
            <ns1:criterionTargetList>
              <ns1:targetListId>100000005</ns1:targetListId>
              <ns1:targetListName>デフォルトリスト</ns1:targetListName>
            </ns1:criterionTargetList>
            <ns1:excludedType>INCLUDED</ns1:excludedType>
            <ns1:bidMultiplier>1</ns1:bidMultiplier>
            <ns1:targetAll>DEACTIVE</ns1:targetAll>
          </ns1:adGroupRetargetingList>
        </ns1:values>
      </ns1:rval>
    </ns1:getResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(ADD)
広告グループレベルでのターゲットリスト設定を追加します。

#### リクエスト
| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupRetargetingListOperation](../data/AdGroupRetargetingListOperation.md) | 広告グループレベルでのターゲットリスト設定と処理の内容です。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      <ns1:accountId>1000000001</ns1:accountId>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutate>
      <ns1:operations>
        <ns1:operator>ADD</ns1:operator>
        <ns1:accountId>100000001</ns1:accountId>
        <ns1:operand>
          <ns1:campaignId>100000002</ns1:campaignId>
          <ns1:adGroupId>100000003</ns1:adGroupId>
          <ns1:criterionTargetList>
            <ns1:targetListId>100000005</ns1:targetListId>
          </ns1:criterionTargetList>
          <ns1:excludedType>INCLUDED</ns1:excludedType>
        </ns1:operand>
        <ns1:operand>
          <ns1:campaignId>100000002</ns1:campaignId>
          <ns1:adGroupId>100000004</ns1:adGroupId>
          <ns1:criterionTargetList>
            <ns1:targetListId>100000005</ns1:targetListId>
          </ns1:criterionTargetList>
          <ns1:excludedType>EXCLUDED</ns1:excludedType>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupRetargetingListReturnValue](../data/AdGroupRetargetingListReturnValue.md) | 広告グループレベルでのターゲットリスト設定に関する情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>AdGroupRetargetingListService</ns1:service>
      <ns1:remainingQuota>74980</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>1.148</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>AdGroupRetargetingListReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>ADD</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupRetargetingList>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:campaignId>100000002</ns1:campaignId>
            <ns1:campaignName>SampleCampaign</ns1:campaignName>
            <ns1:adGroupId>100000003</ns1:adGroupId>
            <ns1:adGroupName>SampleAdGroup1</ns1:adGroupName>
            <ns1:criterionTargetList>
              <ns1:targetListId>100000005</ns1:targetListId>
              <ns1:targetListName>デフォルトリスト</ns1:targetListName>
            </ns1:criterionTargetList>
            <ns1:excludedType>EXCLUDED</ns1:excludedType>
            <ns1:targetAll>DEACTIVE</ns1:targetAll>
          </ns1:adGroupRetargetingList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupRetargetingList>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:campaignId>100000002</ns1:campaignId>
            <ns1:campaignName>SampleCampaign</ns1:campaignName>
            <ns1:adGroupId>100000004</ns1:adGroupId>
            <ns1:adGroupName>SampleAdGroup2</ns1:adGroupName>
            <ns1:criterionTargetList>
              <ns1:targetListId>100000005</ns1:targetListId>
              <ns1:targetListName>デフォルトリスト</ns1:targetListName>
            </ns1:criterionTargetList>
            <ns1:excludedType>INCLUDED</ns1:excludedType>
            <ns1:bidMultiplier>1</ns1:bidMultiplier>
            <ns1:targetAll>DEACTIVE</ns1:targetAll>
          </ns1:adGroupRetargetingList>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(SET)
広告グループレベルでのターゲットリスト設定を更新します。

#### リクエスト

| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupRetargetingListOperation](../data/AdGroupRetargetingListOperation.md) | 広告グループレベルでのターゲットリスト設定と処理の内容です。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      <ns1:accountId>1000000001</ns1:accountId>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutate>
      <ns1:operations>
        <ns1:operator>SET</ns1:operator>
        <ns1:accountId>100000001</ns1:accountId>
        <ns1:operand>
          <ns1:campaignId>100000002</ns1:campaignId>
          <ns1:adGroupId>100000003</ns1:adGroupId>
          <ns1:criterionTargetList>
            <ns1:targetListId>100000005</ns1:targetListId>
          </ns1:criterionTargetList>
          <ns1:excludedType>INCLUDED</ns1:excludedType>
        </ns1:operand>
        <ns1:operand>
          <ns1:campaignId>100000002</ns1:campaignId>
          <ns1:adGroupId>100000004</ns1:adGroupId>
          <ns1:criterionTargetList>
            <ns1:targetListId>100000005</ns1:targetListId>
          </ns1:criterionTargetList>
          <ns1:excludedType>EXCLUDED</ns1:excludedType>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupRetargetingListReturnValue](../data/AdGroupRetargetingListReturnValue.md) | 広告グループレベルでのターゲットリスト設定に関する情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>AdGroupRetargetingListService</ns1:service>
      <ns1:remainingQuota>74980</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>1.148</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>AdGroupRetargetingListReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>SET</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupRetargetingList>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:campaignId>100000002</ns1:campaignId>
            <ns1:campaignName>SampleCampaign</ns1:campaignName>
            <ns1:adGroupId>100000003</ns1:adGroupId>
            <ns1:adGroupName>SampleAdGroup1</ns1:adGroupName>
            <ns1:criterionTargetList>
              <ns1:targetListId>100000005</ns1:targetListId>
              <ns1:targetListName>デフォルトリスト</ns1:targetListName>
            </ns1:criterionTargetList>
            <ns1:excludedType>EXCLUDED</ns1:excludedType>
            <ns1:targetAll>DEACTIVE</ns1:targetAll>
          </ns1:adGroupRetargetingList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupRetargetingList>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:campaignId>100000002</ns1:campaignId>
            <ns1:campaignName>SampleCampaign</ns1:campaignName>
            <ns1:adGroupId>100000004</ns1:adGroupId>
            <ns1:adGroupName>SampleAdGroup2</ns1:adGroupName>
            <ns1:criterionTargetList>
              <ns1:targetListId>100000005</ns1:targetListId>
              <ns1:targetListName>デフォルトリスト</ns1:targetListName>
            </ns1:criterionTargetList>
            <ns1:excludedType>INCLUDED</ns1:excludedType>
            <ns1:bidMultiplier>1</ns1:bidMultiplier>
            <ns1:targetAll>DEACTIVE</ns1:targetAll>
          </ns1:adGroupRetargetingList>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## mutate(REMOVE)
広告グループレベルでのターゲットリスト設定を削除します。

#### リクエスト

| パラメータ | 必須 | 値 | 説明 | 
|---|---|---|---|
| operations | ○ | [AdGroupRetargetingListOperation](../data/AdGroupRetargetingListOperation.md) | 広告グループレベルでのターゲットリスト設定と処理の内容です。 | 

##### ＜リクエストサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:RequestHeader>
      <ns1:license>xxxxxxxxxxxxxxx</ns1:license>
      <ns1:apiAccountId>xxxxxxxxxxxxxxxxxx</ns1:apiAccountId>
      <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
      <ns1:accountId>1000000001</ns1:accountId>
    </ns1:RequestHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutate>
      <ns1:operations>
        <ns1:operator>REMOVE</ns1:operator>
        <ns1:accountId>100000001</ns1:accountId>
        <ns1:operand>
          <ns1:campaignId>100000002</ns1:campaignId>
          <ns1:adGroupId>100000003</ns1:adGroupId>
          <ns1:criterionTargetList>
            <ns1:targetListId>100000005</ns1:targetListId>
          </ns1:criterionTargetList>
          <ns1:excludedType>INCLUDED</ns1:excludedType>
        </ns1:operand>
        <ns1:operand>
          <ns1:campaignId>100000002</ns1:campaignId>
          <ns1:adGroupId>100000004</ns1:adGroupId>
          <ns1:criterionTargetList>
            <ns1:targetListId>100000005</ns1:targetListId>
          </ns1:criterionTargetList>
          <ns1:excludedType>EXCLUDED</ns1:excludedType>
        </ns1:operand>
      </ns1:operations>
    </ns1:mutate>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

#### レスポンス
正常時のレスポンスフィールド

| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [AdGroupRetargetingListReturnValue](../data/AdGroupRetargetingListReturnValue.md) | 広告グループレベルでのターゲットリスト設定に関する情報のコンテナです。 | 

##### ＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="http://ss.yahooapis.jp/V6">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>AdGroupRetargetingListService</ns1:service>
      <ns1:remainingQuota>74980</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>2</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>1.148</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:mutateResponse>
      <ns1:rval>
        <ns1:ListReturnValue.Type>AdGroupRetargetingListReturnValue</ns1:ListReturnValue.Type>
        <ns1:Operation.Type>REMOVE</ns1:Operation.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupRetargetingList>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:campaignId>100000002</ns1:campaignId>
            <ns1:campaignName>SampleCampaign</ns1:campaignName>
            <ns1:adGroupId>100000003</ns1:adGroupId>
            <ns1:adGroupName>SampleAdGroup1</ns1:adGroupName>
            <ns1:criterionTargetList>
              <ns1:targetListId>100000005</ns1:targetListId>
              <ns1:targetListName>デフォルトリスト</ns1:targetListName>
            </ns1:criterionTargetList>
            <ns1:excludedType>EXCLUDED</ns1:excludedType>
            <ns1:targetAll>DEACTIVE</ns1:targetAll>
          </ns1:adGroupRetargetingList>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:adGroupRetargetingList>
            <ns1:accountId>100000001</ns1:accountId>
            <ns1:campaignId>100000002</ns1:campaignId>
            <ns1:campaignName>SampleCampaign</ns1:campaignName>
            <ns1:adGroupId>100000004</ns1:adGroupId>
            <ns1:adGroupName>SampleAdGroup2</ns1:adGroupName>
            <ns1:criterionTargetList>
              <ns1:targetListId>100000005</ns1:targetListId>
              <ns1:targetListName>デフォルトリスト</ns1:targetListName>
            </ns1:criterionTargetList>
            <ns1:excludedType>INCLUDED</ns1:excludedType>
            <ns1:bidMultiplier>1</ns1:bidMultiplier>
            <ns1:targetAll>DEACTIVE</ns1:targetAll>
          </ns1:adGroupRetargetingList>
        </ns1:values>
      </ns1:rval>
    </ns1:mutateResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
