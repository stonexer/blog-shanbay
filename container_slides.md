
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
# Container
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
  