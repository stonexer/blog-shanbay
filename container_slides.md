
# <del>Best</del> Good Practice in Redux-React
## Container & Component
### SToneX
---
# Component
---
## *Campaigns.js* at **soup_web**  
```javascript
class CampaignsList extends Component {
    constructor(props) {
    	this.state = {campaigns:{}}
    }

    componentDidMount() {
        dispatch(fetchCampaign);
    }
    
    render() {
        return (
       	    <table>{campaigns}</table>
        );
    }
}
```
---
Campaign **Fetching Data** & **Present** at the same time.


# Can't Be Reused
>except exactly same situation

---
# Data & Present
---
- ## Fat vs Skinny
- ## Smart vs Dumb
- ## Stateful vs Pure
- ## Screens vs Components
- ...

---
# Container vs Component

---
> A container does data fetching and then renders its corresponding sub-component. That's it. 
> Jason Bonta @ facebook

---
```javascript
class CampaignsContainer extends Component {
    constructor(props) {
    	this.state = {campaigns:{}}
    }

    componentDidMount() {
        dispatch(fetchCampaign);
    }
    
    render() {
        return (
            <CampaignsList
                campaigns={this.state.campaigns}
            />;
        );
    }
}
```

---
```javascript
class CampaignsList extends Component {
    render() {
    	const {campaigns} = this.props
        return (
            <table>{campaigns}</table>
        );
    }
}

CamaignsList.propTypes = {}
```

---
* Separated our data-fetching and rendering
* CampaignsList component reusable
* CampaignsList the ability to set PropTypes

---
# Clear boundary

---
# Component
- how things look
- component inside and *no container inside*
- know nothing about redux
- data & on... from props
- only have UI states
- *Examples: List, Form, Pager, Info...*

---
# Container
- how things work
- only component inside and *no container inside*
- data & handle... to components
- state & action from redux
- have own states

---
# Benefits

- UI / DATA
- Better reusability
- Division of work
- Unit Test

---
# Introduce & Design
- 
