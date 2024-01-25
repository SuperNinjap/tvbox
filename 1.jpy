// 无搜索功能
import { _ } from './lib/cat.js';
let key = '视聚场';
let HOST = 'http://api.cntv.cn';
let siteKey = '';
let siteType = 0;
const MOBILE_UA = 'Mozilla/5.0 (Linux; Android 11; M2007J3SC Build/RKQ1.200826.002; wv) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/77.0.3865.120 MQQBrowser/6.2 TBS/045714 Mobile Safari/537.36';

async function request(reqUrl, agentSp) {
    let res = await req(reqUrl, {
        method: 'get',
        headers: {
            'User-Agent': agentSp || MOBILE_UA,
        },
    });
    return res.content
}

async function init(cfg) {
    siteKey = cfg.skey;
    siteType = cfg.stype
}

async function home(filter) {
    const classes = [{ type_id: "TOPC1451528971114112", type_name: "新闻联播" }, { type_id: "TOPC1451558976694518", type_name: "焦点访谈" }, { type_id: "TOPC1451464665008914", type_name: "今日说法" }, { type_id: "TOPC1451378757637200", type_name: "等着我" }, { type_id: "TOPC1451559129520755", type_name: "新闻直播间" }, { type_id: "TOPC1451540328102649", type_name: "海峡两岸" }, { type_id: "TOPC1451530382483536", type_name: "天网" }, { type_id: "TOPC1451540389082713", type_name: "今日关注" }, { type_id: "TOPC1451557893544236", type_name: "探索·发现" }, {type_id:"TOPC1451557421544786",type_name:"地理中国"},{type_id:"TOPC1451542824484472",type_name:"法律讲堂"},{type_id:"TOPC1571034869935436",type_name:"国宝发现"},{type_id:"TOPC1451540268188575",type_name:"国宝档案"},{type_id:"TOPC1579401761622774",type_name:"名家书场"},{ type_id: "TOPC1665739007799851", type_name: "高端访谈" }, { type_id: "TOPC1451557052519584", type_name: "百家讲坛" }, { type_id: "TOPC1451464884159276", type_name: "开讲啦" }, { type_id: "TOPC1451464884159276", type_name: "故事里的中国" }, { type_id: "TOPC1514182710380601", type_name: "对话" }, { type_id: "TOPC1451559038345600", type_name: "面对面" }, { type_id: "TOPC1451378967257534", type_name: "动物世界" }, {type_id:"TOPC1451984181884527",type_name:"动物传奇"},{ type_id: "TOPC1451558190239536", type_name: "走进科学" }, { type_id: "TOPC1451525103989666", type_name: "人与自然" }, { type_id: "TOPC1451557421544786", type_name: "地理·中国" }, { type_id: "TOPC1451541349400938", type_name: "远方的家" }, { type_id: "TOPC1451558150787467", type_name: "自然传奇" }, { type_id: "TOPC1451534366388377", type_name: "是真的吗" }, { type_id: "TOPC1451467630488780", type_name: "星光大道" }, { type_id: "TOPC1451557646802924", type_name: "健康之路" }, { type_id: "TOPC1451559025546574", type_name: "动画大放映" }, { type_id: "TOPC1451378857272262", type_name: "第一动画乐园" }, { type_id: "TOPC1451541414450906", type_name: "精彩音乐汇" }, { type_id: "TOPC1451534421925242", type_name: "音乐厅" }, { type_id: "TOPC1451541994820527", type_name: "民歌·中国" }, { type_id: "TOPC1575253587571324", type_name: "跟着书本去旅行" }, { type_id: "TOPC1451354597100320", type_name: "中国电影报道" }, { type_id: "TOPC1451469943519994", type_name: "星推荐" }, { type_id: "TOPC1571217727564820", type_name: "方圆剧阵" }, { type_id: "TOPC1451558856402351", type_name: "空中剧院" }, { type_id: "TOPC1650782829200997", type_name: "正大综艺" }, { type_id: "TOPC1451550970356385", type_name: "体坛快讯" }, { type_id: "TOPC1451530259915198", type_name: "第一时间" }, { type_id: "TOPC1451465894294259", type_name: "开门大吉" }, { type_id: "TOPC1451464884159276", type_name: "开讲啦" }, { type_id: "TOPC1451558858788377", type_name: "共同关注" }, { type_id: "TOPC1451527941788652", type_name: "军事报道" }, { type_id: "TOPC1451558819463311", type_name: "新闻调查" }, { type_id: "TOPC1451559097947700", type_name: "新闻30分" }, { type_id: "TOPC1451559066181661", type_name: "新闻1+1" }, { type_id: "TOPC1451540448405749", type_name: "今日亚洲" }, { type_id: "TOPC1451559129520755", type_name: "新闻直播间" }, { type_id: "TOPC1451558428005729", type_name: "24小时" }, { type_id: "TOPC1451539894330405", type_name: "中国新闻" }, { type_id: "TOPC1451558779639282", type_name: "午夜新闻" }, { type_id: "TOPC1451558496100826", type_name: "朝闻天下" }, { type_id: "TOPC1451528792881669", type_name: "晚间新闻" }, { type_id: "TOPC1451559180488841", type_name: "新闻周刊" }, { type_id: "TOPC1601362002656197", type_name: "经济半小时" }, { type_id: "TOPC1451533652476962", type_name: "经济大讲堂" }, { type_id: "TOPC1453100395512779", type_name: "正点财经" }, { type_id: "TOPC1451546588784893", type_name: "生活圈" }, { type_id: "TOPC1451526037568184", type_name: "生活提示" }, { type_id: "TOPC1451558532019883", type_name: "东方时空" }, { type_id: "TOPC1451533782742171", type_name: "经济信息联播" }, { type_id: "TOPC1571034705435323", type_name: "今日环球" }, { type_id: "TOPC1451543462858283", type_name: "一线" },{type_id:"TOPC1564109434999268",type_name:"军武零距离"},{type_id:"TOPC1564110696628209",type_name:"兵器面面观"},{type_id:"TOPC1451528087494889",type_name:"军事科技"},{type_id:"TOPC1564109356650207",type_name:"军事制高点"},{type_id:"TOPC1649983616689859",type_name:"砺剑"},{type_id:"TOPC1451527993718730",type_name:"军事纪实"},{type_id:"TOPC1564110396694880",type_name:"世界战史"},{type_id:"TOPC1564109813378483",type_name:"国防科工"},{type_id:"TOPC1462504102545692",type_name:"军情时间到"},{type_id:"TOPC1451526241359341",type_name:"讲武堂"},{type_id:"TOPC1570876640457386",type_name:"解码科技史"},{type_id:"TOPC1451532939300997",type_name:"回家吃饭"},{type_id:"TOPC1467078331998524",type_name:"遇见大咖"},{type_id:"TOPC1473235107169415",type_name:"国家记忆"},{type_id:"TOPC1458109953138295",type_name:"国家舆论场"},{type_id:"TOPC1451540328102649",type_name:"海峡两岸"},{type_id:"TOPC1451540389082713",type_name:"今日关注"},{type_id:"TOPC1451526164984187",type_name:"防务新观察"},{type_id:"TOPC1451558858788377",type_name:"共同关注"},{type_id:"TOPC1451540709098112",type_name:"深度国际"},{type_id:"TOPC1451558926200436",type_name:"环宇视线"},{type_id:"TOPC1451558687534149",type_name:"世界周刊"},{type_id:"TOPC1451558650605123",type_name:"每周质量报告"	},{type_id:"TOPC1451531385787654",type_name:"天下财经"},{type_id:"TOPC1482483166133803",type_name:"味道"},{type_id:"TOPC1570025984977611",type_name:"中国节拍"},{type_id:"TOPC1451558692971175",type_name:"一鸣惊人"},{type_id:"TOPC1611826337610628",type_name:"金牌喜剧班"},{type_id:"TOPC1451558399948678",type_name:"九洲大戏台"},{type_id:"TOPC1563179546003162",type_name:"乡村大舞台"},{type_id:"TOPC1451375222891702",type_name:"家庭幽默大赛"},{type_id:"TOPC1451985071887935",type_name:"综艺盛典"},{type_id:"TOPC1571300682556971",type_name:"环球综艺"},{type_id:"TOPC1528685010104859",type_name:"广场舞金曲"},{type_id:"TOPC1451984417763860",type_name:"曲艺杂谈"},{type_id:"TOPC1451558363250650",type_name:"锦绣梨园"},{type_id:"TOPC1574909786070351",type_name:"梨园周刊"},{type_id:"TOPC1451541113743615",type_name:"外国人在中国"},{type_id:"TOPC1451539822927345",type_name:"华人世界"},{type_id:"TOPC1451551891055866",type_name:"武林大会"},{type_id:"TOPC1451550531682936",type_name:"棋牌乐"},{type_id:"TOPC1571034804976375",type_name:"美食中国"},{type_id:"TOPC1563178908227191",type_name:"田间示范秀"},{type_id:"TOPC1600745974233265",type_name:"三农群英会"},{type_id:"TOPC1568966531726705",type_name:"乡村振兴面对面"},{type_id:"TOPC1597627647957699",type_name:"超级新农人"},{type_id:"TOPC1563178734372977",type_name:"印象乡村"	}	{type_id:"TOPC1451551777876756",type_name:"天下足球"},{type_id:"TOPC1451549958391444",type_name:"篮球公园"}];
    const filterObj = {};
    return JSON.stringify({
        class: _.map(classes, (cls) => {
            cls.land = 1;
            cls.ratio = 1.78;
            return cls;
        }),
        filters: filterObj,
    })
}

async function homeVod() {
    const data = JSON.parse(await request(HOST + '/NewVideo/getVideoListByColumn?id=TOPC1451558856402351&n=10&sort=desc&p=1&mode=0&serviceId=tvcctv'));
    let videos = _.map(data.data.list, (it) => {
        return {
            vod_id: it.guid,
            vod_name: it.title,
            vod_pic: it.image,
            vod_remarks: it.time || '',
        }
    });
    return JSON.stringify({
        list: videos,
    })
}

async function category(tid, pg, filter, extend) {
    if (pg <= 0 || typeof pg == 'undefined') pg = 1;
    const data = JSON.parse(await request(HOST + '/NewVideo/getVideoListByColumn?id=' + tid + '&n=10&sort=desc&p=' + pg + '&mode=0&serviceId=tvcctv'));
    let videos = _.map(data.data.list, (it) => {
        return {
            vod_id: it.guid,
            vod_name: it.title,
            vod_pic: it.image,
            vod_remarks: it.time || '',
        }
    });
    const pgChk = JSON.parse(await request(HOST + '/NewVideo/getVideoListByColumn?id=' + tid + '&n=10&sort=desc&p=' + (parseInt(pg) + 1) + '&mode=0&serviceId=tvcctv')).data.list;
    const pgCount = pgChk.length > 0 ? parseInt(pg) + 1 : parseInt(pg);
    return JSON.stringify({
        page: parseInt(pg),
        pagecount: parseInt(pgCount),
        limit: 10,
        total: parseInt(data.total),
        list: videos,
    })
}

async function detail(id) {
    const vod = {
        vod_id: id,
        vod_remarks: '',
    };
    const playlist = ['点击播放' + '$' + 'https://hls.cntv.myhwcdn.cn/asp/hls/2000/0303000a/3/default/' + id + '/2000.m3u8'];
    vod.vod_play_from = key;
    vod.vod_play_url = playlist.join('#');
    return JSON.stringify({
        list: [vod],
    });
}

async function play(flag, id, flags) {
    // console.debug('视聚场 id =====>' + id); // js_debug.log
    return JSON.stringify({
        parse: 0,
        url: id,
    })
}

async function search(wd, quick, pg) {
    return '{}'
}

export function __jsEvalReturn() {
    return {
        init: init,
        home: home,
        homeVod: homeVod,
        category: category,
        detail: detail,
        play: play,
        search: search,
    }
}