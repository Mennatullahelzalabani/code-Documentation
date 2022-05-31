# code-documntation
# Chapter 3 
## Screens 
- Creating Event

  - We used some constants to store data in our database 
  
      a.	Constant for creating Event title 

      b.	Constant for creating Brief Summary in Event

      c.	Constant for setting start date and end date for the Event

      d.	Constant for selecting number of participants in the Event

      e.	Constant for uploading Image about Event

      f.	Constant for Event Progress

      g.	Constant for task completion
  
  ```   const [eventTitle, setEventTitle] = useState('');
  const [briefSummary, setBriefSummary] = useState('');
  const [date, setDate] = useState('');
  const [noParticipants, setNoParticipents] = useState(''); 
  const uploadImage =async()=>{
    const storage = firebase.storage();
    const childPath=`post/${firebase.auth().currentUser.uid}/${Math.random().toString(36)}`;
    const uri =props.route.params.image;
    const response =await fetch(uri);
    const blob = await response.blob();
        const task =firebase
        .storage()
        .ref()
        .child(childPath)
        .put(blob)
    const taskProgress = snapshot =>{
    console.log(`transferred: ${snapshot.bytesTransferred}`)
    }
    const taskCompleted = (snapshot)=>{
        task.snapshot.ref.getDownloadURL().then((snapshot)=>{
            savePostData(snapshot);
            savePostHomeData(snapshot)
            console.log(snapshot)
        })
    }
    const taskError =snapshot =>{
        console.log(snapshot)
    }
    
- Creating Activity 

  - We used some constants to store data in our database 
  
    a.	Constant for creating Activity name
    
    b.	Constant for setting start date and end date for the Activity
    
    c.	Constant for setting Activity location
    
    d.	Constant for setting Activity Details
    
    ``` const [activityName, setActivityName] = useState('')
    const [startDate, setStartDate] = useState('');
    const [endDate, setEndDate] = useState('');
    const [location, setLocation] = useState('');
    const [details, setDetails] = useState('');
    const savePostData=()=>{
      firebase.firestore().collection("posts")
      .doc(firebase.auth().currentUser.uid)
      .collection("event")
      .doc(props.route.params.id)
      .collection("Activities")
      
 - Choosing Goals

   - We used a constant to select specific goals in checkbox   

```const checkboxes = [
  { id: 1, text: "Checkbox 1" },
  { id: 2, text: "Checkbox 2" },
  { id: 3, text: "Checkbox 3" }
];

      


 



