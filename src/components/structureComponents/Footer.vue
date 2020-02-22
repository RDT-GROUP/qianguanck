<template>
    <div id="Footer">
        <hr>
        <div class="col-md-12">
            <div class="col-md-8" id="title">
                <div class="col-md-2"></div>
                <div class="col-md-6">
                    <h3>Contact us</h3>
                </div>
            </div>
        </div>
        <div class="col-md-12">
            <div class="col-md-8">
                <div class="col-md-2"></div>
                <div class="col-md-6">
                    <table>
                    <tr v-for="contactItem in contactInfo" :key="contactItem">
                        <td>{{contactItem.content1}}</td>
                        <td class="tbinfo">{{contactItem.content2}}</td>
                    </tr>
                </table>
                </div>
            </div>
        </div>
        <div class="col-md-12">
            <div class="col-md-8">
                <div class="col-md-2"></div>
                <div class="col-md-6">
                    <p style="text-align: left; white-space: pre-wrap;">&copy;{{cpright}}</p>
                </div>
            </div>
            <p><a href="#" style="color: #D0D0D0;">Back to top ↑</a></p>
        </div>
    </div>
</template>

<script type="text/javascript">
export default {
	data () {
		return {
			contactInfo: [{
				content1: '邮箱：',
				content2: 'service@xaqgck.com',
			},
			{
				content1: '电话：',
				content2: '12312312345',
			},
			{
				content1: '地址：',
				content2: '陕西省西安市碑林区二环南路西段69号',
			}],
			cpright: ' 2019 Xi\'an Qianguan Measurement and control Co., Ltd'
		}
	}
}
</script>

<style>
    #Footer {
		height: 170px;
		background-color: #FFFFFF;
	}
    .tbinfo {
        text-align: left;
    }
    .pull-right {
        margin-right: 15%;
    }
    #title {
        text-align: left;
    }
    h3 {
        margin-top: 0.05%;
    }
</style>
