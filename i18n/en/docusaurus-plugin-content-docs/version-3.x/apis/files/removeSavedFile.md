---
title: Taro.removeSavedFile(option)
sidebar_label: removeSavedFile
---

Deletes local cache files.

> [Reference](https://developers.weixin.qq.com/miniprogram/en/dev/api/file/wx.removeSavedFile.html)

## Type

```tsx
(option: Option) => Promise<CallbackResult>
```

## Parameters

### Option

<table>
  <thead>
    <tr>
      <th>Property</th>
      <th>Type</th>
      <th style={{ textAlign: "center"}}>Required</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>filePath</td>
      <td><code>string</code></td>
      <td style={{ textAlign: "center"}}>Yes</td>
      <td>Path to the file to be deleted</td>
    </tr>
    <tr>
      <td>complete</td>
      <td><code>(res: any) =&gt; void</code></td>
      <td style={{ textAlign: "center"}}>No</td>
      <td>The callback function used when the API call completed (always executed whether the call succeeds or fails)</td>
    </tr>
    <tr>
      <td>fail</td>
      <td><code>(res: any) =&gt; void</code></td>
      <td style={{ textAlign: "center"}}>No</td>
      <td>The callback function for a failed API call</td>
    </tr>
    <tr>
      <td>success</td>
      <td><code>(res: Result) =&gt; void</code></td>
      <td style={{ textAlign: "center"}}>No</td>
      <td>The callback function for a successful API call</td>
    </tr>
  </tbody>
</table>

### RemoveSavedFileFailCallbackResult

<table>
  <thead>
    <tr>
      <th>Property</th>
      <th>Type</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>errMsg</td>
      <td><code>string</code></td>
      <td>Error message<br /><br />valid value: <br />- 'fail file not exist';</td>
    </tr>
  </tbody>
</table>

## Sample Code

```tsx
Taro.getSavedFileList({
  success: function (res) {
    if (res.fileList.length > 0){
      Taro.removeSavedFile({
        filePath: res.fileList[0].filePath,
        complete: function (res) {
          console.log(res)
        }
      })
    }
  }
})
```

## API Support

| API | WeChat Mini-Program | H5 | React Native |
| :---: | :---: | :---: | :---: |
| Taro.removeSavedFile | ✔️ |  | ✔️ |
