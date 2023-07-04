>Link跳转
```javascript
   import Link from 'next/link'

   export default function Postistf({posts}){
      return (
         <div><Link href={"./dasb"}>go dasb</Link></div>
      )
   }
```

>useRouter编程式
```javascript
'use client';

import { useRouter } from 'next/navigetion';

export default function Page (){

   const router = useRouter();

   return (
      <button onClick={() => router.push('/desh')}>dash<button/>
   )
}
```