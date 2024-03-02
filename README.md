import React, { useState } from 'react'

export default function Forms() {
    const[forms,setform]=useState('')
    const[password,setpassword]=useState('')
    const[submit,setsubmit]=useState([])

    const hanldesubmit=(e)=>{
e.preventDefault();
let dataentry={name:forms,password:password}
// console.log(dataentry)
setsubmit((e)=>[...e,dataentry])
console.log(submit)

    }
  return (
    <div>
    <form action="" onSubmit={hanldesubmit}>
    <input type="text" value={forms} onChange={(e)=>setform(e.target.value)} />
    <input type="text" value={password} onChange={(e)=>setpassword(e.target.value)} />
    <button>submit</button>
    </form>
    

    <h6>
    {
        submit.map((ele,index)=>{
            return(
                <div key={index}>
                <h1>{ele.name}</h1>
                <h1>{ele.password}</h1>
                </div>
            )
        })
    }
    </h6>
    </div>
  )
}
