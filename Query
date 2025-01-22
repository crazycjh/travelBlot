'use client'
import { useState } from 'react'

import axios from 'axios'
import { marked }  from 'marked'

const Query = () => {
  const [data, setData] = useState("")
  marked.setOptions({
    gfm: true, // 支援 GitHub 標記語法
    breaks: true, // 支援換行符
    sanitize: true, // 禁用 HTML 標籤（提高安全性）
  });

  
  const getTravelDetail = async () => {
    // 使用 axios
    // fetch('https://chc-dify.zeabur.app/v1/workflows/run', {
    //   method: 'POST',
    //   headers: {
    //     'Content-Type': 'application/json',
    //     Authorization: 'Bearer app-ABVIWmqqTci3gTXy1C7V4hUf',
    //   },
    //   body: JSON.stringify({
    //     inputs: {
    //       cities: '蘇黎世',
    //     },
    //     response_mode: 'blocking',
    //     user: 'abc-123',
    //   }),
    // }).then((res) => {
    //   console.log(res)
    // })

    const res = await axios.post('https://chc-dify.zeabur.app/v1/workflows/run', {
      inputs: {
        cities: '蘇黎世',
      },
      response_mode: 'blocking',
      user: 'abc-123',
    }, {
      headers: {
        'Content-Type': 'application/json',
        Authorization: 'Bearer app-ABVIWmqqTci3gTXy1C7V4hUf',
      },
    })
    console.log(res)
    
    const resData = res.data.data.outputs
    
    console.log(resData)
    // const result = resData.text.replace(/\\n/g, '\n');
    setData(marked(resData.text))
  }

  return (
    <div>
      <button onClick={getTravelDetail}>Query 拉</button>
      <div>
      <div dangerouslySetInnerHTML={{ __html: data }} />
      </div>
    </div>
  )
}

export default Query