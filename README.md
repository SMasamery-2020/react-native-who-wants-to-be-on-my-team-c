import React, { Component } from 'react';
import { AppRegistry, Text, View, StyleSheet, Dimensions, TouchableHighlight } from 'react-native';
import Constants from 'expo-constants';

let deviceHeight = Dimensions.get('window').height;
let deviceWidth = Dimensions.get('window').width;

export default class App extends Component {
    state={
        UnoPageDisplay:'block',
        DosPageDisplay:'none',
        TresPageDisplay:'none',
    }
    handleUnoPagePress= () => this.setState(state => ({
        UnoPageDisplay:'block',
        DosPageDisplay:'none',
        TresPageDisplay:'none',
    }));
    
    handleDosPagePress= () => this.setState(state =>({
       UnoPageDisplay:'none',
       DosPageDisplay:'block',
       TresPageDisplay:'none',
    }));
    
    handleTresPagePress=() =>this.setState(state=>({
       UnoPageDisplay:'none',
       DosPageDisplay:'none',
       TresPageDisplay:'block',
    }));
    render() {
        return (
            <View styles={styles.container}>
                <View style={styles.BContain}>
                    <TouchableHighlight style={styles.Buttons}
                    onPress={this.handleUnoPagePress}>
                        <Text style={styles.BText}>
                            1
                        </Text>
                    </TouchableHighlight>
                    <TouchableHighlight style={styles.Buttons}
                    onPress={this.handleDosPagePress}>
                        <Text style={styles.BText}>
                            2
                        </Text>
                    </TouchableHighlight>
                    <TouchableHighlight style={styles.Buttons}
                    onPress={this.handleTresPagePress}>
                        <Text style={styles.BText}>
                            3
                        </Text>
                    </TouchableHighlight>
                </View>
                <View style={{display: this.state.UnoPageDisplay}}>
                    <Text style={styles.text}>
                        bankruptcy
                    </Text>
                </View>
                
                <View style={{display: this.state.DosPageDisplay}}>
                    <Text style={styles.text}>
                        omg
                    </Text>
                </View>
                
                <View style={{display: this.state.TresPageDisplay}}>
                    <Text style={styles.text}>
                        Tamale
                    </Text>
                </View>
            </View>
        );
    }
}

const styles = StyleSheet.create({
    container: {
        flex: 1,
        alignItems: 'center',
        justifyContent: 'center',
        paddingTop: Constants.statusBarHeight,
        backgroundColor: '#ecf0f1',
    },
    paragraph: {
        margin: 24,
        fontSize: 18,
        fontWeight: 'bold',
        textAlign: 'center',
        color: '#34495e',
    },
    text:{
        fontSize:14,
        textAlign:'center',
    },
    BContain:{
        top:0,
        backgroundColor:'lightgray',
        alignItems:'center',
        justifyContent:'center',
        width:deviceWidth,
        height:35,
        flexDirection:'row',
    },
    Buttons:{
        backgroundColor:'white',
        width:deviceWidth/12,
        height:deviceHeight/16,
        width:15,
        margin: 15,
        alignItems:'center',
        justifyContent:'center',
        borderWidth:1,
        borderColor:'black',
    },
    BText:{
        fontWeight:'bold',
        fontSize:21,
        color:'darkblue',
    },
});
