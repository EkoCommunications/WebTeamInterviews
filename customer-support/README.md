```jsx
import { useState, useEffect } from "react";
import { getUser } from "@amityco/ts-sdk";

export const UserProfile = ({ showIf, userId }) => {
  const [visible, defineVis] = useState(false)
  const [user, setUser] = useState({})
  
  useEffect(() => {
    if (showIf) defineVis(false);
    else defineVis(true);
  }, [showIf]);
  
  useEffect(() => {

    Promise.resolve()
      .then(() => defineVis(false)
      .then(() => getUser(userId))
      .then(setUser)
      .then(() => defineVis(true))
    
  }, [userId])
  
  if (!visible) return null
  
  return <div>JSON.stringify(user, null, 2)</div>
}
```
